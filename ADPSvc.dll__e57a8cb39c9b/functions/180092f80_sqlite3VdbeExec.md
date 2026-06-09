# sqlite3VdbeExec

- ea: `0x180092f80`
- end: `0x18009954e`
- name: `sqlite3VdbeExec`
- size: `26062`
- prototype: ``
- caller_count: `2`
- callee_count: `173`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180039e48`
- `0x1800abe70`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x1800034f2`
- `0x180035fc4`
- `0x180037540`
- `0x1800375b4`
- `0x18003a4a4`
- `0x18003ad84`
- `0x180046574`
- `0x1800468a0`
- `0x18004a544`
- `0x180058aec`
- `0x180059210`
- `0x180067168`
- `0x1800688dc`
- `0x18006a5f4`
- `0x18006a66c`
- `0x18006a6d0`
- `0x18006a6fc`
- `0x18006a7b0`
- `0x18006a7c8`
- `0x18006acb0`
- `0x18006ada8`
- `0x18006ae10`
- `0x18006ae90`
- `0x18006aea0`
- `0x18006aeac`
- `0x18006aeb8`
- `0x18006b30c`
- `0x18006b374`
- `0x18006b398`
- `0x18006b3a8`
- `0x18006b458`
- `0x18006b53c`
- `0x18006b648`
- `0x18006baac`
- `0x18006bfdc`
- `0x18006bffc`
- `0x18006c414`
- `0x18006c434`
- `0x18006c444`
- `0x18006c464`
- `0x18006c51c`
- `0x18006c580`
- `0x18006c5c8`
- `0x18006cc6c`
- `0x18006ccac`
- `0x18006cccc`
- `0x18006ce9c`
- `0x18006cef8`

## string_xrefs

- `0x180099057`: `cannot open savepoint - SQL statements in progress`
- `0x180098f88`: `cannot commit transaction - SQL statements in progress`
- `0x180099032`: `cannot rollback - no transaction is active`
- `0x180099039`: `cannot commit - no transaction is active`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1, __int64 a2)
{
  __int64 v2; // r13
  __int64 v3; // r10
  __int64 *v4; // r15
  __int64 v5; // r8
  unsigned __int8 *v6; // r14
  __int64 v7; // rsi
  unsigned __int64 v8; // r9
  unsigned __int8 v9; // di
  __int64 v10; // r11
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // r12d
  __int64 v15; // rbx
  unsigned __int64 v16; // r9
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  __int64 v20; // r15
  unsigned int v21; // ebx
  __int64 v22; // r12
  __int64 v23; // rsi
  unsigned int JournalMode; // eax
  unsigned int v25; // edi
  __int64 v26; // rax
  unsigned int v27; // eax
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  unsigned int v31; // eax
  __int64 v32; // rdi
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rsi
  __int64 v36; // rdi
  __int64 v37; // rbx
  unsigned int v38; // eax
  int v39; // r8d
  unsigned int v40; // eax
  unsigned int v41; // ebx
  _BYTE *v42; // rsi
  unsigned int v43; // ebx
  __int64 v44; // rbx
  unsigned int v45; // eax
  _QWORD *v46; // rax
  _QWORD *v47; // rdi
  __int64 v48; // rax
  _QWORD *v49; // r15
  unsigned int m; // edi
  int v51; // eax
  unsigned int *v52; // r12
  int v53; // esi
  unsigned int v54; // eax
  int v55; // eax
  __int64 v56; // r8
  unsigned int v57; // eax
  int *v58; // r13
  int v59; // r12d
  __int64 v60; // rcx
  int v61; // ebx
  int v62; // esi
  unsigned int v63; // eax
  int v64; // ebx
  unsigned int v65; // r12d
  __int64 n; // rax
  _QWORD *v67; // rcx
  __int64 v68; // r13
  unsigned int v69; // eax
  __int64 v70; // r9
  unsigned int v71; // eax
  bool v72; // zf
  int v73; // ebx
  int v74; // ebx
  int v75; // ebx
  int v76; // ebx
  __int64 v77; // rcx
  __int64 *v78; // rbx
  int v79; // r9d
  __int64 v80; // rdx
  char v81; // di
  __int64 v82; // r8
  __int64 v83; // rcx
  __int64 v84; // rax
  __int16 v85; // ax
  __int64 v86; // rdx
  __int64 v87; // rdi
  int *v88; // r11
  __int64 v89; // r13
  int v90; // r9d
  __int64 **v91; // rbx
  __int64 v92; // rdx
  __int64 *v93; // r15
  __int64 v94; // rsi
  __int64 v95; // rax
  unsigned int v96; // eax
  __int64 *v97; // rdx
  int v98; // eax
  __int64 v99; // rcx
  int v100; // ebx
  int v101; // ebx
  int v102; // ebx
  int v103; // ebx
  int v104; // eax
  bool v105; // zf
  __int64 v106; // r8
  __int64 v107; // r9
  unsigned __int64 v108; // rcx
  unsigned int v109; // edx
  int v110; // eax
  int v111; // eax
  int v112; // eax
  __int64 v113; // rax
  __int64 v114; // rbx
  __int16 v115; // ax
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // rcx
  int v119; // eax
  __int64 v120; // rcx
  __int64 v121; // rax
  int v122; // r13d
  __int64 v123; // rsi
  __int64 v124; // rdi
  __int16 v125; // r15
  __int64 v126; // rax
  __int16 v127; // cx
  __int64 v128; // r12
  _BYTE *v129; // rcx
  BOOL v130; // ecx
  __int64 v131; // rdx
  __int64 v132; // rax
  __int64 v133; // rbx
  int v134; // eax
  unsigned __int64 v135; // rdx
  __int64 v136; // rcx
  __int64 v137; // rcx
  __int64 v138; // rcx
  __int64 v139; // rcx
  __int16 v140; // ax
  int v141; // ecx
  bool v142; // zf
  __int64 v143; // rcx
  __int64 v144; // rax
  __int64 v145; // rbx
  __int64 v146; // rcx
  int *v147; // rsi
  __int64 v148; // rdx
  unsigned int v149; // eax
  int v150; // eax
  _QWORD *v151; // rdi
  unsigned int v152; // eax
  char v153; // r15
  __int64 v154; // rax
  unsigned int v155; // eax
  unsigned int v156; // eax
  __int64 v157; // rcx
  __int64 v158; // rax
  __int64 v159; // rbx
  unsigned int v160; // eax
  __int64 v161; // rcx
  __int64 v162; // rax
  __int64 v163; // rcx
  __int128 v164; // xmm1
  __int128 v165; // xmm0
  __int64 v166; // rdi
  __int64 v167; // rbx
  __int64 v168; // rcx
  unsigned int v169; // eax
  bool v170; // zf
  __int64 v171; // rax
  __int64 v172; // rdi
  int v173; // ecx
  unsigned int v174; // edx
  int v175; // ebx
  int v176; // ebx
  int v177; // ebx
  int v178; // ebx
  __int64 v179; // rbx
  unsigned int v180; // eax
  __int64 v181; // rcx
  __int64 v182; // rax
  __int64 v183; // rbx
  unsigned int v184; // eax
  int v185; // ebx
  int v186; // eax
  int v187; // ebx
  __int64 *v188; // rax
  __int64 v189; // r8
  __int64 v190; // rdx
  __int16 v191; // cx
  __int16 v192; // cx
  __int64 v193; // rcx
  __int64 v194; // rax
  __int64 v195; // rdx
  __int64 v196; // rcx
  __int64 v197; // rbx
  unsigned int v198; // edi
  unsigned int v199; // eax
  int v200; // ebx
  int v201; // ecx
  int v202; // ebx
  int v203; // ebx
  int v204; // ebx
  int v205; // ebx
  int v206; // ebx
  bool v207; // zf
  bool v208; // zf
  __int64 v209; // r8
  __int64 jj; // rax
  int *v211; // r12
  int *v212; // r13
  __int64 v213; // rsi
  int v214; // edi
  int v215; // r15d
  __int64 v216; // rbx
  __int64 v217; // rcx
  __int64 *v218; // rsi
  __int64 v219; // rdx
  __int64 v220; // r15
  __int64 v221; // rcx
  void *v222; // rcx
  __int64 v223; // r8
  int v224; // eax
  int v225; // edi
  __int64 v226; // rbx
  __int64 v227; // rsi
  int v228; // eax
  __int64 v229; // rsi
  bool v230; // sf
  int v231; // eax
  __int64 v232; // rax
  __int64 v233; // rbx
  __int64 v234; // r13
  __int64 v235; // r15
  __int16 v236; // si
  __int16 v237; // di
  bool v238; // zf
  __int64 v239; // rax
  char v240; // cl
  __int64 v241; // rcx
  char v242; // cl
  unsigned __int8 v243; // al
  int v244; // eax
  int v245; // ebx
  int v246; // ebx
  int v247; // ebx
  int v248; // ebx
  unsigned int v249; // eax
  __int64 v250; // rcx
  __int64 v251; // rax
  __int64 v252; // rax
  __int64 v253; // rcx
  __int64 v254; // rax
  __int64 v255; // rdx
  __int64 v256; // rcx
  __int64 v257; // rdi
  __int64 **v258; // rcx
  __int64 *v259; // rbx
  __int64 v260; // rsi
  int v261; // eax
  int v262; // ebx
  int v263; // ebx
  int v264; // ebx
  __int64 v265; // rax
  __int64 v266; // rbx
  __int64 v267; // rdi
  int v268; // edx
  int v269; // eax
  const char *v270; // rax
  __int64 v271; // rbx
  unsigned __int64 v272; // rax
  unsigned __int64 v273; // rdx
  int v274; // r8d
  unsigned __int8 v275; // cf
  __int64 v276; // rdx
  __int64 v277; // rcx
  int v278; // ebx
  int v279; // ebx
  int v280; // ebx
  int v281; // ebx
  __int64 v282; // rax
  unsigned int **v283; // rax
  unsigned int *v284; // rcx
  __int64 v285; // rcx
  __int64 v286; // rax
  __int64 v287; // rax
  int v288; // eax
  int v289; // ebx
  int v290; // ebx
  int v291; // ebx
  int v292; // ebx
  int v293; // esi
  __int64 v294; // rdi
  __int64 v295; // rbx
  int v296; // eax
  __int64 v297; // rdi
  int v298; // eax
  __int64 v299; // rbx
  __int64 v300; // rax
  __int64 v301; // rdx
  __int64 v302; // rbx
  int v303; // eax
  __int64 v304; // rcx
  __int64 v305; // rbx
  int v306; // edi
  __int16 v307; // si
  __int16 v308; // si
  int v309; // esi
  __int64 v310; // rdi
  __int64 kk; // rbx
  int v312; // eax
  __int16 v313; // ax
  int v314; // ebx
  int v315; // ebx
  int v316; // ebx
  int v317; // ebx
  __int64 v318; // rax
  __int64 v319; // rax
  __int64 v320; // r8
  __int64 v321; // rdx
  __int64 v322; // rcx
  _QWORD *v323; // rbx
  int v324; // ebx
  int v325; // ebx
  int v326; // ebx
  __int64 v327; // rsi
  int v328; // eax
  unsigned int v329; // edi
  unsigned int *v330; // r8
  unsigned int v331; // r9d
  int v332; // ecx
  int v333; // edx
  __int64 v334; // r12
  int v335; // r13d
  __int64 v336; // r15
  unsigned int v337; // eax
  __int64 v338; // rbx
  unsigned int v339; // eax
  __int64 v340; // rax
  int v341; // ebx
  int v342; // ebx
  int v343; // ebx
  int v344; // ebx
  __int64 v345; // rcx
  __int64 v346; // rax
  __int64 v347; // rcx
  unsigned int v348; // eax
  unsigned int **v349; // rax
  unsigned int *v350; // rdx
  char *v351; // rdi
  __int64 v352; // r15
  int v353; // r13d
  int v354; // r12d
  int v355; // eax
  int *v356; // rcx
  int *v357; // rsi
  char v358; // al
  int *v359; // rbx
  __int16 v360; // ax
  int *v361; // rax
  int *j; // rbx
  __int16 v363; // cx
  unsigned __int64 v364; // rdx
  int v365; // edx
  __int64 v366; // rax
  __int64 v367; // rcx
  __int64 v368; // rax
  double v369; // xmm0_8
  unsigned int v370; // edi
  unsigned int v371; // esi
  __int64 v372; // rax
  int v373; // eax
  int v374; // ecx
  unsigned __int64 v375; // rax
  __int64 v376; // rdi
  int v377; // edx
  unsigned __int64 v378; // rax
  int v379; // ecx
  unsigned __int64 v380; // rax
  __int64 v381; // rbx
  unsigned int *v382; // r15
  int v383; // eax
  _BYTE *v384; // rdi
  _BYTE *v385; // rbx
  _BYTE *v386; // rsi
  int *v387; // rdi
  __int64 v388; // r15
  __int64 v389; // rax
  unsigned __int64 v390; // rcx
  __int64 v391; // rdx
  int v392; // eax
  int v393; // eax
  int v394; // eax
  int v395; // eax
  unsigned __int64 v396; // rcx
  unsigned __int64 v397; // rcx
  int v398; // eax
  char *v399; // rdi
  char v400; // al
  __int64 i; // rbx
  __int16 v402; // cx
  __int16 v403; // cx
  __int64 v404; // r12
  __int64 v405; // r15
  __int64 v406; // rdi
  int v407; // esi
  _WORD *v408; // r9
  bool v409; // zf
  __int16 v410; // ax
  bool v411; // zf
  const char *v412; // rax
  __int64 v413; // rax
  unsigned int v414; // r12d
  __int64 v415; // rbx
  unsigned int *v416; // r13
  int v417; // eax
  __int64 v418; // rdi
  __int64 v419; // rdx
  int v420; // eax
  unsigned int v421; // eax
  unsigned int v422; // eax
  unsigned int *v423; // r15
  unsigned __int8 *Payload; // rcx
  __int64 v425; // rcx
  int v426; // eax
  int *v427; // rdi
  unsigned int v428; // eax
  int v429; // eax
  unsigned __int16 *v430; // rsi
  __int64 v431; // rcx
  __int64 v432; // rax
  __int64 v433; // rcx
  unsigned int v434; // eax
  __int64 v435; // r12
  unsigned int v436; // r14d
  unsigned __int8 *v437; // rdi
  unsigned __int64 v438; // rsi
  unsigned __int64 v439; // r13
  unsigned int *v440; // rcx
  __int64 v441; // rax
  int v442; // edi
  __int64 v443; // rdx
  int v444; // eax
  __int64 v445; // rax
  __int64 v446; // rdi
  const void *v447; // rsi
  size_t v448; // rbx
  __int64 v449; // rdx
  char v450; // al
  unsigned int v451; // eax
  unsigned int v452; // eax
  __int64 v453; // rcx
  __int64 v454; // rdx
  __int64 v455; // rax
  int v456; // ebx
  int v457; // ebx
  int v458; // ebx
  __int64 v459; // rdi
  __int64 v460; // rdx
  __int64 v461; // rsi
  __int64 v462; // rdi
  __int64 v463; // rbx
  __int64 v464; // rdi
  __int64 v465; // rbx
  unsigned int updated; // eax
  __int64 k; // rax
  __int64 v468; // rbx
  __int64 v469; // rax
  char v470; // cl
  __int64 v471; // rdx
  int v472; // ebx
  int v473; // ebx
  int v474; // ebx
  __int64 v475; // rax
  __int64 v476; // rdi
  __int64 v477; // rsi
  __int64 v478; // r15
  __int16 v479; // dx
  unsigned __int8 v480; // bl
  int v481; // ecx
  __int64 v482; // rdx
  __int64 v483; // r8
  int v484; // ecx
  int v485; // ecx
  int v486; // ecx
  __int128 v487; // rax
  __int64 v488; // rax
  int v489; // eax
  __int16 v490; // ax
  double v491; // xmm6_8
  double v492; // xmm0_8
  __int64 v493; // rbx
  __int64 v494; // rax
  double v495; // xmm0_8
  __int16 v496; // ax
  __int64 v497; // r13
  __int16 v498; // r12
  __int64 v499; // rdi
  __int64 v500; // rbx
  int v501; // eax
  __int16 v502; // si
  int v503; // eax
  unsigned __int64 v504; // r15
  int v505; // ebx
  int v506; // ebx
  int v507; // ebx
  __int64 v508; // rbx
  __int64 Cursor; // rax
  int v510; // ecx
  __int64 v511; // rdi
  __int64 v512; // rbx
  int v513; // r12d
  __int64 v514; // rcx
  __int64 v515; // r15
  __int64 v516; // rax
  __int64 v517; // r13
  int v518; // esi
  unsigned __int8 v519; // cl
  unsigned __int8 v520; // al
  __int64 v521; // rbx
  __int64 v522; // r8
  __int64 v523; // rax
  __int64 v524; // rcx
  unsigned int v525; // eax
  int v526; // ebx
  int v527; // ebx
  int v528; // ebx
  int v529; // ebx
  __int64 v530; // rax
  __int64 v531; // rdx
  __int64 v532; // rcx
  __int64 v533; // rax
  __int64 v534; // rdx
  __int64 v535; // rsi
  __int64 v536; // rdx
  __int64 v537; // rcx
  unsigned int v538; // eax
  __int64 v539; // rax
  _QWORD *v540; // r15
  unsigned int v541; // eax
  unsigned int v542; // eax
  __int64 v543; // r13
  _DWORD *v544; // r12
  __int64 v545; // rdi
  unsigned int v546; // ebx
  __int64 v547; // rax
  __int64 v548; // rcx
  __int64 v549; // rax
  __int64 v550; // r9
  __int64 v551; // rdx
  __int64 v552; // rbx
  int v553; // ecx
  __int64 v554; // rcx
  __int64 v555; // rax
  int v556; // ebx
  int v557; // ebx
  int v558; // ebx
  int v559; // ebx
  __int64 v560; // rcx
  __int64 v561; // rdx
  __int64 v562; // rax
  __int64 v563; // rbx
  __int64 v564; // r8
  __int64 v565; // rdi
  __int64 v566; // rsi
  __int16 v567; // r8
  __int64 v568; // r9
  unsigned int v569; // eax
  __int64 v570; // rcx
  void (__fastcall *v571)(_QWORD, __int64, __int64, _QWORD, __int64); // rax
  __int64 v572; // rdx
  __int64 *v573; // rsi
  __int64 v574; // rdi
  unsigned int v575; // eax
  __int64 v576; // rax
  __int64 v577; // rcx
  __int64 *v578; // rbx
  __int64 v579; // rax
  int v580; // ebx
  unsigned int v581; // eax
  _QWORD *v582; // rax
  __int64 v583; // rdx
  __int64 v584; // rdx
  int v585; // eax
  __int64 v586; // rcx
  __int64 v587; // rax
  __int64 v588; // rbx
  int v589; // edi
  __int64 v590; // rax
  unsigned int v591; // eax
  bool v592; // sf
  __int64 v593; // rcx
  unsigned int v594; // eax
  __int64 v595; // r8
  int v596; // ebx
  int v597; // ebx
  int v598; // ebx
  int v599; // ebx
  __int64 v600; // rbx
  __int64 v601; // rdi
  unsigned int v602; // eax
  unsigned int v603; // eax
  int Writeable; // eax
  unsigned int v605; // eax
  __int64 v606; // rcx
  __int64 v607; // r8
  __int64 v608; // rdx
  __int64 v609; // rax
  unsigned int v610; // eax
  int v611; // r15d
  __int64 v612; // rbx
  unsigned int v613; // eax
  __int64 v614; // rax
  __int64 v615; // rdx
  __int64 v616; // rcx
  __int64 v617; // rdi
  __int64 v618; // rbx
  __int64 v619; // rax
  __int64 *v620; // rcx
  __int64 v621; // rbx
  unsigned int v622; // eax
  __int64 v623; // rdi
  __int64 v624; // rbx
  unsigned int v625; // eax
  unsigned int v626; // eax
  __int64 v627; // rax
  __int64 v628; // rcx
  __int64 v629; // rdi
  __int64 v630; // rbx
  unsigned int v631; // eax
  __int16 v632; // r8
  __int64 v633; // rcx
  __int64 v634; // r9
  __int64 v635; // rcx
  __int64 v636; // rax
  __int64 v637; // rdi
  __int64 v638; // rsi
  __int64 v639; // rcx
  int IsValidNN; // eax
  unsigned int v641; // eax
  __int64 v642; // rdx
  __int64 v643; // rbx
  __int64 valid; // rax
  __int64 v645; // rcx
  __int64 v646; // rax
  _QWORD *v647; // rbx
  __int64 v648; // rdi
  __int64 v649; // rax
  unsigned int v650; // eax
  __int64 v651; // rdx
  unsigned int v652; // eax
  int v653; // eax
  int v654; // ebx
  int v655; // ebx
  int v656; // ebx
  int v657; // ebx
  __int64 v658; // rcx
  __int64 v659; // rdx
  __int64 v660; // rax
  unsigned int v661; // eax
  __int64 v662; // rdx
  __int64 v663; // rbx
  unsigned int v664; // edi
  __int64 v665; // rcx
  __int64 v666; // rdx
  __int64 v667; // rcx
  __int64 v668; // rcx
  __int64 v669; // rax
  __int64 v670; // rbx
  unsigned int v671; // eax
  unsigned int v672; // eax
  __int64 v673; // rdx
  __int64 v674; // rcx
  __int64 v675; // r8
  int v676; // ebx
  int v677; // ebx
  int v678; // ebx
  int v679; // ebx
  __int64 v680; // rbx
  __int64 v681; // rcx
  unsigned int inited; // eax
  __int64 v683; // rbx
  int v684; // eax
  __int64 v685; // r8
  __int64 v686; // rbx
  __int64 v687; // rbx
  char v688; // di
  int v689; // esi
  unsigned int v690; // eax
  const char *v691; // r8
  __int64 v692; // rax
  __int64 v693; // rcx
  _QWORD *v694; // rbx
  __int64 v695; // r8
  __int64 v696; // r9
  unsigned int v697; // eax
  int v698; // ebx
  int v699; // ebx
  int v700; // ebx
  int v701; // ebx
  __int64 v702; // rax
  __int64 v703; // rdi
  __int64 v704; // rbx
  __int64 v705; // rdx
  __int64 v706; // r8
  __int64 v707; // rdi
  int v708; // eax
  __int64 v709; // rdx
  int v710; // r9d
  __int64 v711; // rbx
  __int64 v712; // r9
  unsigned __int64 v713; // rsi
  __int64 (__fastcall *v714)(_QWORD); // rax
  __int64 v715; // rbx
  int v716; // eax
  __int64 v717; // rcx
  int v718; // ebx
  int v719; // ebx
  __int64 v720; // rdi
  __int64 v721; // rbx
  __int64 v722; // rcx
  _DWORD *v723; // rbx
  __int64 v724; // r8
  int v725; // edx
  __int64 v726; // rsi
  __int64 v727; // rbx
  __int64 v728; // rdx
  __int64 v729; // rdx
  int v730; // eax
  __int64 v731; // rcx
  _QWORD *v732; // rdi
  _QWORD *v733; // rbx
  _DWORD *v734; // r8
  __int64 v735; // rax
  __int64 v736; // rdx
  int v737; // eax
  const char *v738; // rax
  int v739; // ebx
  int v740; // ebx
  int v741; // ebx
  int v742; // ebx
  __int64 v743; // rbx
  unsigned int v744; // eax
  int v745; // ebx
  int v746; // ebx
  int v747; // ebx
  __int64 v748; // rax
  __int64 *v749; // rbx
  __int64 v750; // rdi
  __int64 v751; // r9
  __int64 v752; // rax
  __int64 v753; // rax
  __int64 v754; // rax
  __int64 v755; // rbx
  unsigned int v756; // eax
  __int64 v757; // rax
  __int64 v758; // r15
  _QWORD *v759; // rsi
  __int64 v760; // rcx
  __int64 *v761; // rdi
  __int64 v762; // rbx
  __int64 v763; // r9
  int v764; // ebx
  int v765; // ebx
  int v766; // ebx
  int v767; // ebx
  _QWORD *v768; // rdi
  __int64 v769; // rdx
  __int64 v770; // rbx
  unsigned int Page; // eax
  _QWORD *v772; // rbx
  int v773; // esi
  __int64 v774; // rbx
  __int64 v775; // rdi
  unsigned int v776; // eax
  __int64 v777; // rdi
  __int64 v778; // rax
  __int64 v779; // rbx
  __int64 *v780; // rsi
  __int64 v781; // r15
  __int16 v782; // ax
  unsigned int v783; // eax
  const char *v784; // rax
  __int64 v785; // rdi
  _QWORD *v786; // rax
  _QWORD *v787; // rbx
  __int64 v788; // rax
  int v789; // ebx
  int v790; // ebx
  int v791; // ebx
  char v792; // al
  const char *v793; // r9
  __int64 v794; // rbx
  __int64 v795; // rbx
  int v796; // eax
  int ii; // ecx
  __int64 v798; // rax
  __int64 v799; // rbx
  unsigned __int64 v800; // rax
  unsigned __int64 v801; // r8
  __int64 v802; // rdx
  __int64 v803; // rcx
  __int64 v804; // rdx
  const char *v805; // r8
  const char *v806; // rdx
  int v807; // ebx
  int v808; // ecx
  char v809; // al
  const char *v810; // rdx
  unsigned int v811; // eax
  int v812; // ecx
  unsigned int v813; // eax
  __int64 v814; // rbx
  const char *v815; // rax
  unsigned __int64 v816; // rdx
  __int64 (__fastcall *v817)(__int64); // rax
  __int64 v818; // rcx
  int v819; // eax
  __int64 v821; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v822; // [rsp+48h] [rbp-C0h]
  unsigned int v823; // [rsp+4Ch] [rbp-BCh]
  unsigned int Table; // [rsp+50h] [rbp-B8h]
  __int64 v825; // [rsp+58h] [rbp-B0h]
  __int64 v826; // [rsp+60h] [rbp-A8h]
  unsigned int *v828; // [rsp+70h] [rbp-98h] BYREF
  __int64 v829; // [rsp+78h] [rbp-90h] BYREF
  __int64 v830; // [rsp+80h] [rbp-88h]
  int *v831; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v832; // [rsp+90h] [rbp-78h] BYREF
  char v833; // [rsp+94h] [rbp-74h]
  unsigned int v834; // [rsp+98h] [rbp-70h]
  __int128 v835; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v836; // [rsp+B0h] [rbp-58h]
  __int128 v837; // [rsp+C0h] [rbp-48h]
  int v838; // [rsp+D0h] [rbp-38h]
  __int64 v839; // [rsp+D8h] [rbp-30h] BYREF
  int v840; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v841; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v842; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v843; // [rsp+F8h] [rbp-10h]
  __int128 v844; // [rsp+100h] [rbp-8h] BYREF
  __int128 v845; // [rsp+110h] [rbp+8h]
  __int128 v846; // [rsp+120h] [rbp+18h]
  __int64 v847; // [rsp+130h] [rbp+28h]
  __int128 v848; // [rsp+138h] [rbp+30h] BYREF
  __int128 v849; // [rsp+148h] [rbp+40h]
  __int128 v850; // [rsp+158h] [rbp+50h]
  __int64 v851; // [rsp+168h] [rbp+60h]
  _OWORD v852[2]; // [rsp+170h] [rbp+68h] BYREF
  __int128 v853; // [rsp+190h] [rbp+88h]
  __int64 v854; // [rsp+1A0h] [rbp+98h]
  char v855; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v856; // [rsp+1A9h] [rbp+A1h]
  char v857; // [rsp+1ABh] [rbp+A3h]
  int v858; // [rsp+1ACh] [rbp+A4h]
  int v859; // [rsp+1F8h] [rbp+F0h]
  __int64 v860; // [rsp+1FCh] [rbp+F4h] BYREF

  v2 = *a1;
  v3 = 0;
  v4 = a1;
  v5 = a1[17];
  v6 = (unsigned __int8 *)v5;
  v7 = a1[13];
  v8 = 0;
  v9 = *(_BYTE *)(*a1 + 100);
  v822 = v9;
  v825 = v5;
  v830 = *a1;
  v833 = 0;
  v843 = 0;
  v826 = v7;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter(a1, a2, v5, 0);
    v8 = v843;
    v5 = (__int64)v6;
    v3 = 0;
  }
  if ( *(_QWORD *)(v2 + 528) )
    v842 = (unsigned int)(*(_DWORD *)(v2 + 544) - *((_DWORD *)v4 + 57) % *(_DWORD *)(v2 + 544));
  else
    v842 = -1;
  v10 = 1;
  if ( *((_DWORD *)v4 + 13) == 7 )
    goto LABEL_1543;
  *((_DWORD *)v4 + 13) = 0;
  v4[9] = 0;
  v11 = *(_DWORD *)(v2 + 408);
  *(_DWORD *)(v2 + 664) = 0;
  if ( v11 )
    goto LABEL_1536;
  v12 = *((int *)v4 + 12);
  v13 = 0;
  v14 = 0;
  Table = 0;
  v823 = 0;
  v838 = 0;
  v6 = (unsigned __int8 *)(v5 + 24 * v12);
LABEL_9:
  v15 = *v6;
  v16 = v10 + v8;
  v839 = (__int64)v6;
  v843 = v16;
  if ( (unsigned int)v15 > 0x5C )
  {
    if ( (unsigned int)v15 <= 0x8C )
    {
      if ( (_DWORD)v15 == 140 )
      {
        v645 = *((int *)v6 + 1);
        LODWORD(v829) = 0;
        *(_QWORD *)&v837 = 0;
        v646 = v4[15];
        v835 = 0;
        v836 = 0;
        v647 = *(_QWORD **)(v646 + 8 * v645);
        v648 = v647[6];
        *(_QWORD *)&v835 = v647[7];
        WORD6(v836) = *((_WORD *)v6 + 6);
        v649 = *((int *)v6 + 2);
        BYTE14(v836) = 0;
        *((_QWORD *)&v835 + 1) = v7 + 56 * v649;
        v650 = sqlite3BtreeIndexMoveto(v648, &v835, &v829);
        v3 = 0;
        Table = v650;
        v14 = v650;
        if ( v650 )
          goto LABEL_1546;
        if ( (_DWORD)v829 )
        {
          if ( *((_WORD *)v6 + 1) )
          {
            v653 = sqlite3WritableSchema(v2);
            v3 = 0;
            if ( !v653 )
            {
              v811 = sqlite3ReportError(779, 99938, "index corruption");
              goto LABEL_1530;
            }
          }
        }
        else
        {
          LOBYTE(v651) = 4;
          v652 = sqlite3BtreeDelete(v648, v651);
          v3 = 0;
          Table = v652;
          v14 = v652;
          if ( v652 )
            goto LABEL_1546;
        }
        v647[4] = 0;
        goto LABEL_80;
      }
      if ( (unsigned int)v15 <= 0x74 )
      {
        if ( (_DWORD)v15 != 116 )
        {
          if ( (unsigned int)v15 <= 0x69 )
          {
            if ( (_DWORD)v15 == 105 )
              goto LABEL_880;
            if ( (unsigned int)v15 <= 0x63 )
            {
              if ( (_DWORD)v15 == 99 )
              {
                v453 = *(_QWORD *)(v2 + 32);
                v454 = *((unsigned int *)v6 + 3);
                v455 = 32LL * *((int *)v6 + 1);
                LODWORD(v829) = 0;
                sqlite3BtreeGetMeta(*(_QWORD *)(v455 + v453 + 8), v454, &v829);
                v283 = (unsigned int **)out2Prerelease(v4, v6);
                v284 = (unsigned int *)(int)v829;
                goto LABEL_536;
              }
              v341 = v15 - 94;
              if ( v341 )
              {
                v342 = v341 - 1;
                if ( v342 )
                {
                  v343 = v342 - 1;
                  if ( !v343 )
                  {
                    v399 = (char *)*((_QWORD *)v6 + 2);
                    v400 = *v399;
                    for ( i = v7 + 56LL * *((int *)v6 + 1); ; i += 56 )
                    {
                      LOBYTE(v5) = v822;
                      LOBYTE(v13) = v400;
                      applyAffinity(i, v13, v5);
                      if ( *v399 == 69 )
                      {
                        v402 = *(_WORD *)(i + 20);
                        if ( (v402 & 4) != 0 )
                        {
                          v13 = *(_QWORD *)i;
                          v5 = 0xFFFFFFFFFFFFLL;
                          if ( (unsigned __int64)(*(_QWORD *)i + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                          {
                            v403 = v402 & 0xFFF1 | 8;
                            *(double *)i = (double)(int)v13;
                          }
                          else
                          {
                            v403 = v402 & 0xFFDB | 0x20;
                          }
                          *(_WORD *)(i + 20) = v403;
                        }
                      }
                      v10 = 1;
                      v3 = 0;
                      v400 = *++v399;
                      if ( !*v399 )
                        break;
                    }
                    goto LABEL_1404;
                  }
                  v344 = v343 - 1;
                  if ( v344 )
                  {
                    if ( v344 != 1 )
                      goto LABEL_53;
                    v345 = *((int *)v6 + 1);
                    v346 = v4[15];
                    v828 = 0;
                    v347 = *(_QWORD *)(v346 + 8 * v345);
                    if ( *((_DWORD *)v6 + 3) )
                    {
                      v828 = (unsigned int *)sqlite3BtreeRowCountEst(*(_QWORD *)(v347 + 48));
                    }
                    else
                    {
                      v348 = sqlite3BtreeCount(v2, *(_QWORD *)(v347 + 48), &v828);
                      v3 = 0;
                      Table = v348;
                      v14 = v348;
                      if ( v348 )
                        goto LABEL_1546;
                    }
                    v349 = (unsigned int **)out2Prerelease(v4, v6);
                    *v349 = v828;
                    goto LABEL_1308;
                  }
                  v350 = 0;
                  v351 = (char *)*((_QWORD *)v6 + 2);
                  v352 = 0;
                  v353 = *((_DWORD *)v6 + 3);
                  v354 = 0;
                  v355 = *((_DWORD *)v6 + 2);
                  v356 = (int *)(v7 + 56LL * *((int *)v6 + 1));
                  LODWORD(v829) = 0;
                  v828 = 0;
                  v831 = v356;
                  v357 = &v356[14 * (v355 - (int)v10)];
                  v839 = (__int64)v357;
                  if ( v351 )
                  {
                    v358 = *v351;
                    v359 = v356;
                    do
                    {
                      LOBYTE(v5) = v822;
                      LOBYTE(v350) = v358;
                      applyAffinity(v359, v350, v5);
                      if ( *v351 == 69 )
                      {
                        v360 = *((_WORD *)v359 + 10);
                        if ( (v360 & 4) != 0 )
                          *((_WORD *)v359 + 10) = v360 & 0xFFDB | 0x20;
                      }
                      v10 = 1;
                      v359 += 14;
                      ++v351;
                      v3 = 0;
                      v358 = *v351;
                    }
                    while ( *v351 );
                    v354 = v829;
                    v350 = v828;
                    v357 = (int *)v839;
                  }
                  v361 = v831;
                  for ( j = v357; ; j -= 14 )
                  {
                    v363 = *((_WORD *)j + 10);
                    if ( ((unsigned __int8)v363 & (unsigned __int8)v10) != 0 )
                    {
                      j[9] = (v363 & 0x400) != 0 ? 0xA : 0;
                      v354 += v10;
                    }
                    else
                    {
                      if ( (v363 & 0x24) != 0 )
                      {
                        v364 = *(_QWORD *)j;
                        if ( *(__int64 *)j < 0 )
                          v364 = ~v364;
                        v354 += v10;
                        if ( v364 <= 0x7F )
                        {
                          if ( (v10 & *(_QWORD *)j) == *(_QWORD *)j && *((_BYTE *)a1 + 197) >= 4u )
                          {
                            v365 = v364 + 8;
                          }
                          else
                          {
                            v352 += v10;
                            v365 = v10;
                          }
                          v366 = 36;
                          v367 = (__int64)j;
                          goto LABEL_684;
                        }
                        if ( v364 <= 0x7FFF )
                        {
                          v368 = 2;
                          goto LABEL_673;
                        }
                        if ( v364 > 0x7FFFFF )
                        {
                          if ( v364 > 0x7FFFFFFF )
                          {
                            if ( v364 > 0x7FFFFFFFFFFFLL )
                            {
                              v352 += 8;
                              if ( (v363 & 0x20) != 0 )
                              {
                                v369 = (double)(int)*(_QWORD *)j;
                                v365 = 7;
                                *((_WORD *)j + 10) = v363 & 0xFFD7 | 8;
                                *(double *)j = v369;
                              }
                              else
                              {
                                v365 = 6;
                              }
                            }
                            else
                            {
                              v352 += 6;
                              v365 = 5;
                            }
                          }
                          else
                          {
                            v368 = 4;
LABEL_673:
                            v352 += v368;
                            v365 = v368;
                          }
                        }
                        else
                        {
                          v352 += 3;
                          v365 = 3;
                        }
                        v367 = 36;
                        v366 = (__int64)j;
LABEL_684:
                        *(_DWORD *)(v367 + v366) = v365;
                        goto LABEL_696;
                      }
                      if ( (v363 & 8) != 0 )
                      {
                        v354 += v10;
                        j[9] = 7;
                        v352 += 8;
                        goto LABEL_697;
                      }
                      v370 = j[4];
                      v371 = ((v363 & 2 | 0x18u) >> 1) + 2 * v370;
                      if ( (v363 & 0x400) != 0 )
                      {
                        v372 = *j;
                        v371 += 2 * v372;
                        if ( v352 )
                        {
                          v373 = sqlite3VdbeMemExpandBlob(j);
                          v3 = 0;
                          if ( v373 )
                            goto LABEL_1541;
                          v370 += *j;
                          v10 = 1;
                        }
                        else
                        {
                          v828 = (unsigned int *)((char *)v350 + v372);
                        }
                      }
                      v374 = v10;
                      v352 += v370;
                      v375 = v371;
                      while ( 1 )
                      {
                        v375 >>= 7;
                        if ( !v375 )
                          break;
                        v374 += v10;
                      }
                      v354 += v374;
                      j[9] = v371;
                    }
LABEL_696:
                    v361 = v831;
LABEL_697:
                    if ( j == v361 )
                    {
                      v376 = v826 + 56LL * v353;
                      if ( v354 <= 126 )
                        goto LABEL_707;
                      v377 = v10;
                      v378 = v354;
                      while ( 1 )
                      {
                        v378 >>= 7;
                        if ( !v378 )
                          break;
                        v377 += v10;
                      }
                      v354 += v377;
                      v379 = v10;
                      v380 = v354;
                      while ( 1 )
                      {
                        v380 >>= 7;
                        if ( !v380 )
                          break;
                        v379 += v10;
                      }
                      if ( v377 < v379 )
LABEL_707:
                        v354 += v10;
                      v381 = v352 + v354;
                      v382 = v828;
                      if ( (__int64)v828 + v381 <= *(int *)(v376 + 32) )
                      {
                        *(_QWORD *)(v376 + 8) = *(_QWORD *)(v376 + 40);
                        goto LABEL_712;
                      }
                      v2 = v830;
                      if ( (__int64)v828 + v381 <= *(int *)(v830 + 136) )
                      {
                        v383 = sqlite3VdbeMemClearAndResize(v376, (unsigned int)v381);
                        v3 = 0;
                        if ( v383 )
                          goto LABEL_858;
LABEL_712:
                        *(_DWORD *)(v376 + 16) = v381;
                        *(_WORD *)(v376 + 20) = 16;
                        if ( v382 )
                        {
                          *(_DWORD *)v376 = (_DWORD)v382;
                          *(_WORD *)(v376 + 20) = 1040;
                        }
                        v384 = *(_BYTE **)(v376 + 8);
                        v385 = &v384[v354];
                        if ( v354 >= 128 )
                        {
                          v386 = &v384[(int)sqlite3PutVarint(v384, v354)];
                          v3 = 0;
                        }
                        else
                        {
                          *v384 = v354;
                          v386 = v384 + 1;
                        }
                        v387 = v831;
                        v388 = v839;
                        while ( 2 )
                        {
                          v389 = (unsigned int)v387[9];
                          if ( (unsigned int)v389 <= 7 )
                          {
                            v10 = 1;
                            *v386++ = v389;
                            if ( (_DWORD)v389 )
                            {
                              v390 = *(_QWORD *)v387;
                              v391 = *((unsigned __int8 *)qword_1800FB9C0 + v389);
                              v392 = *((unsigned __int8 *)qword_1800FB9C0 + v389) - 1;
                              if ( v392 )
                              {
                                v393 = v392 - 1;
                                if ( v393 )
                                {
                                  v394 = v393 - 1;
                                  if ( v394 )
                                  {
                                    v395 = v394 - 1;
                                    if ( v395 )
                                    {
                                      if ( v395 != 2 )
                                      {
                                        v385[7] = v390;
                                        v396 = v390 >> 8;
                                        v385[6] = v396;
                                        v390 = v396 >> 8;
                                      }
                                      v385[5] = v390;
                                      v397 = v390 >> 8;
                                      v385[4] = v397;
                                      v390 = v397 >> 8;
                                    }
                                    v385[3] = v390;
                                    v390 >>= 8;
                                  }
                                  v385[2] = v390;
                                  v390 >>= 8;
                                }
                                v385[1] = v390;
                                v390 >>= 8;
                              }
                              *v385 = v390;
                              v385 += v391;
                            }
                            goto LABEL_738;
                          }
                          if ( (unsigned int)v389 >= 0x80 )
                          {
                            v398 = sqlite3PutVarint(v386, (unsigned int)v387[9]);
                            v3 = 0;
                            v386 += v398;
                            if ( v387[4] )
                              goto LABEL_736;
LABEL_737:
                            v10 = 1;
                          }
                          else
                          {
                            v10 = 1;
                            *v386++ = v389;
                            if ( (unsigned int)v389 >= 0xE && v387[4] > 0 )
                            {
LABEL_736:
                              memcpy_0(v385, *((const void **)v387 + 1), v387[4]);
                              v385 += v387[4];
                              v3 = 0;
                              goto LABEL_737;
                            }
                          }
LABEL_738:
                          if ( v387 == (int *)v388 )
                          {
                            v14 = Table;
                            v4 = a1;
                            goto LABEL_1403;
                          }
                          v387 += 14;
                          continue;
                        }
                      }
LABEL_1527:
                      v4 = a1;
LABEL_1528:
                      sqlite3VdbeError(v4, "string or blob too big");
                      v14 = 18;
                      goto LABEL_1523;
                    }
                    v350 = v828;
                  }
                }
                v404 = *((_QWORD *)v6 + 2);
                v405 = *(_QWORD *)(v404 + 8);
                v406 = v7 + 56LL * *((int *)v6 + 1);
                v407 = 0;
                if ( *(__int16 *)(v404 + 54) > 0 )
                {
                  while ( (*(_BYTE *)(v405 + 24LL * v407 + 18) & 0x60) != 0 )
                  {
                    if ( (*(_BYTE *)(v405 + 24LL * v407 + 18) & 0x20) == 0 )
                    {
                      if ( !*((_DWORD *)v6 + 3) )
                        break;
                      v406 += 56;
                    }
LABEL_773:
                    v407 += v10;
                    if ( v407 >= *(__int16 *)(v404 + 54) )
                    {
                      v14 = Table;
                      v5 = v825;
                      goto LABEL_976;
                    }
                  }
                  LOBYTE(v5) = v822;
                  LOBYTE(v13) = *(_BYTE *)(v405 + 24LL * v407 + 12);
                  applyAffinity(v406, v13, v5);
                  v408 = (_WORD *)(v406 + 20);
                  v10 = 1;
                  v13 = *(unsigned __int16 *)(v406 + 20);
                  if ( (v13 & 1) != 0 )
                    goto LABEL_772;
                  v5 = (*(_DWORD *)(v405 + 24LL * v407 + 8) >> 4) & 0xF;
                  switch ( (*(_DWORD *)(v405 + 24LL * v407 + 8) >> 4) & 0xF )
                  {
                    case 2:
                      v409 = (v13 & 0x10) == 0;
LABEL_771:
                      if ( v409 )
                      {
LABEL_769:
                        v412 = *(const char **)(v405 + 24LL * v407);
                        v4 = a1;
                        sqlite3VdbeError(
                          a1,
                          "cannot store %s value in %s column %s.%s",
                          off_1800CD4E8[*((unsigned __int8 *)qword_1800FE430 + (v13 & 0x3F))],
                          off_18010E5A0[(unsigned int)(v5 - 1)],
                          *(const char **)v404,
                          v412);
                        v14 = 3091;
                        goto LABEL_1523;
                      }
                      goto LABEL_772;
                    case 3:
                    case 4:
                      v411 = (v13 & 4) == 0;
                      break;
                    case 5:
                      if ( (v13 & 4) != 0 )
                      {
                        v5 = 0xFFFFFFFFFFFFLL;
                        if ( (unsigned __int64)(*(_QWORD *)v406 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                        {
                          v410 = v13 | 8;
                          v13 = (unsigned __int16)v13 | 8u;
                          *(double *)v406 = (double)(int)*(_QWORD *)v406;
                        }
                        else
                        {
                          LOWORD(v13) = v13 | 0x20;
                          v410 = v13;
                        }
                        *v408 = v13;
                        *v408 = v410 & 0xFFFB;
                        goto LABEL_772;
                      }
                      v411 = (v13 & 0x28) == 0;
                      break;
                    case 6:
                      v409 = (v13 & 2) == 0;
                      goto LABEL_771;
                    default:
LABEL_772:
                      v406 += 56;
                      v3 = 0;
                      goto LABEL_773;
                  }
                  if ( v411 )
                    goto LABEL_769;
                  goto LABEL_772;
                }
                v14 = Table;
LABEL_977:
                v4 = a1;
                v7 = v826;
                goto LABEL_978;
              }
              v832 = 0;
              v848 = 0;
              v851 = 0;
              v413 = v4[15];
              v849 = 0;
              v850 = 0;
              v414 = *((_DWORD *)v6 + 2);
              v415 = *(_QWORD *)(v413 + 8LL * *((int *)v6 + 1));
LABEL_776:
              LODWORD(v831) = v414;
              while ( 1 )
              {
                v416 = *(unsigned int **)(v415 + 88);
                v417 = *((_DWORD *)v4 + 11);
                v828 = v416;
                if ( *(_DWORD *)(v415 + 32) == v417 )
                {
                  if ( !**(_BYTE **)(v415 + 48) )
                  {
                    v10 = 1;
LABEL_806:
                    v430 = (unsigned __int16 *)(v415 + 74);
                    if ( *(unsigned __int16 *)(v415 + 74) > v414 )
                    {
                      v443 = *(unsigned int *)(v415 + 4LL * v414 + 120);
                      v832 = *(_DWORD *)(v415 + 4LL * v414 + 120);
                      goto LABEL_849;
                    }
                    v427 = (int *)(v415 + 64);
                    if ( *(_DWORD *)(v415 + 64) >= *v416 )
                    {
                      v443 = 0;
                      v832 = 0;
                      goto LABEL_841;
                    }
                    v431 = *(_QWORD *)(v415 + 96);
                    v829 = v431;
                    if ( !v431 )
                    {
                      v848 = 0;
                      v849 = 0;
                      v851 = 0;
                      v850 = 0;
                      v434 = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v415 + 48), *v416, &v848);
                      v3 = 0;
                      Table = v434;
                      v14 = v434;
                      if ( v434 )
                        goto LABEL_1546;
                      v431 = *((_QWORD *)&v848 + 1);
LABEL_811:
                      v829 = v431;
                    }
                    v435 = *v430;
                    v10 = 1;
                    v436 = (unsigned int)v831;
                    v437 = (unsigned __int8 *)(v431 + (unsigned int)*v427);
                    v438 = v416[v435];
                    v439 = v431 + *v416;
                    v440 = v828;
                    do
                    {
                      v832 = *v437;
                      *(_DWORD *)(v415 + 4LL * (int)v435 + 120) = v832;
                      if ( v832 >= 0x80 )
                      {
                        v437 += (unsigned __int8)sqlite3GetVarint32(v437, &v832);
                        *(_DWORD *)(v415 + 4LL * (int)v435 + 120) = v832;
                        if ( v832 < 0x80 )
                          v441 = *((unsigned __int8 *)qword_1800FB9C0 + v832);
                        else
                          v441 = (v832 - 12) >> 1;
                        v440 = v828;
                        v10 = 1;
                      }
                      else
                      {
                        ++v437;
                        v441 = *((unsigned __int8 *)qword_1800FB9C0 + (unsigned __int8)v832);
                      }
                      v438 += v441;
                      LODWORD(v435) = v435 + 1;
                      v440[(int)v435] = v438;
                    }
                    while ( (unsigned int)v435 <= v436 && (unsigned __int64)v437 < v439 );
                    v6 = (unsigned __int8 *)v839;
                    if ( (unsigned __int64)v437 < v439 )
                    {
                      if ( v438 <= *(unsigned int *)(v415 + 104) )
                        goto LABEL_824;
                    }
                    else if ( (unsigned __int64)v437 <= v439 && v438 == *(_DWORD *)(v415 + 104) )
                    {
LABEL_824:
                      v3 = 0;
                      goto LABEL_825;
                    }
                    v3 = 0;
                    if ( !*v440 )
                    {
                      LOWORD(v435) = 0;
                      LODWORD(v437) = v439;
LABEL_825:
                      v442 = (_DWORD)v437 - v829;
                      *(_WORD *)(v415 + 74) = v435;
                      *(_DWORD *)(v415 + 64) = v442;
                      if ( !*(_QWORD *)(v415 + 96) && ((WORD2(v849) & 0x9000) != 0 || (_DWORD)v850) )
                      {
                        vdbeMemClear(&v848);
                        v443 = v832;
                        v3 = 0;
                        v416 = v828;
                        v414 = (unsigned int)v831;
                        v10 = 1;
                      }
                      else
                      {
                        v443 = v832;
                        v416 = v828;
                        v414 = (unsigned int)v831;
                      }
LABEL_841:
                      if ( *(unsigned __int16 *)(v415 + 74) <= v414 )
                      {
                        v7 = v826;
                        v445 = v826 + 56LL * *((int *)v6 + 3);
                        if ( v6[1] == 0xF6 )
                        {
                          sqlite3VdbeMemShallowCopy(v826 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2), 0x2000);
                        }
                        else
                        {
                          if ( (*(_WORD *)(v445 + 20) & 0x9000) == 0 )
                          {
                            v14 = Table;
                            v4 = a1;
                            *(_WORD *)(v445 + 20) = 1;
                            goto LABEL_146;
                          }
                          vdbeMemClearExternAndSetNull(v826 + 56LL * *((int *)v6 + 3));
                        }
LABEL_844:
                        v14 = Table;
                        v4 = a1;
LABEL_422:
                        v9 = v822;
                        goto LABEL_244;
                      }
LABEL_849:
                      v7 = v826;
                      v446 = v826 + 56LL * *((int *)v6 + 3);
                      if ( (*(_WORD *)(v446 + 20) & 0x9000) != 0 )
                      {
                        vdbeMemClearExternAndSetNull(v826 + 56LL * *((int *)v6 + 3));
                        v443 = v832;
                      }
                      if ( *(_DWORD *)(v415 + 108) >= v416[v414 + 1] )
                      {
                        v447 = (const void *)(*(_QWORD *)(v415 + 96) + v416[v414]);
                        if ( (unsigned int)v443 < 0xC )
                        {
                          sqlite3VdbeSerialGet(*(_QWORD *)(v415 + 96) + v416[v414], v443, v446);
                          v14 = Table;
                          goto LABEL_854;
                        }
                        v448 = (unsigned int)(v443 - 12) >> 1;
                        *(_DWORD *)(v446 + 16) = v448;
                        *(_BYTE *)(v446 + 22) = v822;
                        v449 = (unsigned int)(v448 + 2);
                        if ( *(_DWORD *)(v446 + 32) >= (int)v449 )
                        {
                          *(_QWORD *)(v446 + 8) = *(_QWORD *)(v446 + 40);
                        }
                        else
                        {
                          v2 = v830;
                          if ( (int)v448 > *(_DWORD *)(v830 + 136) )
                            goto LABEL_1527;
                          *(_WORD *)(v446 + 20) = 1;
                          if ( (unsigned int)sqlite3VdbeMemGrow(v446, v449, 0) )
                          {
LABEL_858:
                            v4 = a1;
                            goto LABEL_1543;
                          }
                        }
                        memcpy_0(*(void **)(v446 + 8), v447, v448);
                        v14 = Table;
                        v3 = 0;
                        v4 = a1;
                        *(_BYTE *)(v448 + *(_QWORD *)(v446 + 8)) = 0;
                        v10 = 1;
                        *(_BYTE *)(v448 + *(_QWORD *)(v446 + 8) + 1) = 0;
                        *(_WORD *)(v446 + 20) = word_1800FD13C[v832 & 1];
                        goto LABEL_145;
                      }
                      *(_BYTE *)(v446 + 22) = v822;
                      v450 = v6[2] & 0xC0;
                      if ( v450 && (v450 == (char)0x80 || v832 >= 0xC && ((v832 & 1) == 0 || v450 == -64))
                        || (v832 < 0x80
                          ? (v451 = *((unsigned __int8 *)qword_1800FB9C0 + v832))
                          : (v451 = (v832 - 12) >> 1),
                            !v451) )
                      {
                        sqlite3VdbeSerialGet(&qword_1800FB500, v832, v446);
                        goto LABEL_844;
                      }
                      v4 = a1;
                      v452 = vdbeColumnFromOverflow(v415, v414, v832, v416[v414], *((_DWORD *)a1 + 11), v838, v446);
                      v3 = 0;
                      Table = v452;
                      v14 = v452;
                      if ( v452 )
                      {
                        if ( v452 != 7 )
                        {
                          if ( v452 != 18 )
                            goto LABEL_1546;
                          goto LABEL_1528;
                        }
                        goto LABEL_1542;
                      }
LABEL_80:
                      v9 = v822;
LABEL_52:
                      v5 = v825;
                      v10 = 1;
                      v13 = v823;
                      goto LABEL_53;
                    }
                    if ( !*(_QWORD *)(v415 + 96) && ((WORD2(v849) & 0x9000) != 0 || (_DWORD)v850) )
                    {
                      vdbeMemClear(&v848);
                      v3 = 0;
                      v10 = 1;
                    }
LABEL_836:
                    v5 = v825;
                    v444 = *(_DWORD *)(v825 + 12);
                    if ( v444 > 0 )
                    {
                      v14 = Table;
                      v4 = a1;
                      v6 = (unsigned __int8 *)(v825 + 24LL * (v444 - 1));
LABEL_838:
                      v7 = v826;
                      goto LABEL_147;
                    }
                    v14 = sqlite3CorruptError(96592);
LABEL_1522:
                    v4 = a1;
                    goto LABEL_1523;
                  }
                }
                else
                {
                  if ( *(_BYTE *)(v415 + 2) )
                  {
                    if ( *(_BYTE *)v415 == 3 && *(int *)(v415 + 36) > 0 )
                    {
                      v423 = (unsigned int *)(v415 + 108);
                      v425 = 56LL * *(int *)(v415 + 36);
                      v426 = *(_DWORD *)(v425 + v7 + 16);
                      *(_DWORD *)(v415 + 108) = v426;
                      *(_DWORD *)(v415 + 104) = v426;
                      Payload = *(unsigned __int8 **)(v425 + v7 + 8);
LABEL_793:
                      v427 = (int *)(v415 + 64);
                      *(_QWORD *)(v415 + 96) = Payload;
                      *(_DWORD *)(v415 + 32) = *((_DWORD *)a1 + 11);
                      v428 = *Payload;
                      *v416 = v428;
                      if ( v428 >= 0x80 )
                      {
                        LOBYTE(v429) = sqlite3GetVarint32(*(_QWORD *)(v415 + 96), v416);
                        v3 = 0;
                        v429 = (unsigned __int8)v429;
                        v10 = 1;
                      }
                      else
                      {
                        v10 = 1;
                        v429 = 1;
                      }
                      v430 = (unsigned __int16 *)(v415 + 74);
                      *v427 = v429;
                      *(_WORD *)(v415 + 74) = 0;
                      if ( *v423 >= *v416 )
                      {
                        v431 = *(_QWORD *)(v415 + 96);
                        goto LABEL_811;
                      }
                      *(_QWORD *)(v415 + 96) = 0;
                      *v423 = 0;
                      if ( *v416 <= 0x18003 && *v416 <= *(_DWORD *)(v415 + 104) )
                      {
                        v4 = a1;
                        goto LABEL_806;
                      }
                      goto LABEL_836;
                    }
                    v432 = v7 + 56LL * *((int *)v6 + 3);
                    if ( (*(_WORD *)(v432 + 20) & 0x9000) == 0 )
                    {
                      v14 = Table;
                      v10 = 1;
                      *(_WORD *)(v432 + 20) = 1;
                      goto LABEL_146;
                    }
                    v433 = v7 + 56LL * *((int *)v6 + 3);
LABEL_803:
                    vdbeMemClearExternAndSetNull(v433);
                    v14 = Table;
                    goto LABEL_422;
                  }
                  v418 = *(_QWORD *)(v415 + 48);
                  if ( *(_BYTE *)(v415 + 3) )
                  {
                    v419 = *(_QWORD *)(v415 + 16);
                    if ( !v419 || (v420 = *(_DWORD *)(v419 + 4LL * (v414 + 1))) == 0 )
                    {
                      v422 = sqlite3VdbeFinishMoveto(v415);
                      v3 = 0;
                      Table = v422;
                      if ( v422 )
                      {
LABEL_787:
                        v14 = Table;
                        goto LABEL_1546;
                      }
LABEL_789:
                      getCellInfo(v418);
                      v423 = (unsigned int *)(v415 + 108);
                      *(_DWORD *)(v415 + 104) = *(_DWORD *)(v418 + 64);
                      Payload = (unsigned __int8 *)fetchPayload(v418, v415 + 108);
                      v3 = 0;
                      goto LABEL_793;
                    }
                    v415 = *(_QWORD *)(v415 + 40);
                    v414 = v420 - 1;
                    goto LABEL_776;
                  }
                  if ( !*(_BYTE *)v418 )
                    goto LABEL_789;
                }
                v421 = sqlite3VdbeHandleMovedCursor(v415);
                v3 = 0;
                Table = v421;
                if ( v421 )
                  goto LABEL_787;
              }
            }
            v456 = v15 - 100;
            if ( !v456 )
            {
              v464 = *(_QWORD *)(v2 + 32);
              v465 = 32LL * *((int *)v6 + 1);
              updated = sqlite3BtreeUpdateMeta(
                          *(_QWORD *)(v465 + v464 + 8),
                          *((unsigned int *)v6 + 2),
                          *((unsigned int *)v6 + 3));
              v10 = 1;
              Table = updated;
              v14 = updated;
              if ( *((_DWORD *)v6 + 2) == 1 )
              {
                **(_DWORD **)(v465 + v464 + 24) = *((_DWORD *)v6 + 3) - *((unsigned __int16 *)v6 + 1);
                *(_DWORD *)(v2 + 44) |= 1u;
                sqlite3FkClearTriggerCache(v2, *((unsigned int *)v6 + 1));
                v10 = 1;
              }
              else if ( *((_DWORD *)v6 + 2) == 2 )
              {
                *(_BYTE *)(*(_QWORD *)(v465 + v464 + 24) + 112LL) = v6[12];
              }
              v3 = 0;
              if ( *((_DWORD *)v6 + 1) == 1 )
              {
                for ( k = *(_QWORD *)(v2 + 8); k; k = *(_QWORD *)(k + 16) )
                {
                  *(_DWORD *)(k + 200) &= ~2u;
                  *(_DWORD *)(k + 200) |= 1u;
                }
                *((_DWORD *)v4 + 50) &= 0xFFFFFFFC;
              }
LABEL_173:
              if ( !v14 )
                goto LABEL_146;
              goto LABEL_1546;
            }
            v457 = v456 - 1;
            if ( v457 )
            {
              v458 = v457 - 1;
              if ( v458 && (unsigned int)(v458 - 1) > 1 )
                goto LABEL_53;
LABEL_880:
              v459 = v7 + 56LL * *((int *)v6 + 1);
              v460 = v7 + 56LL * *((int *)v6 + 2);
              v461 = 56LL * *((int *)v6 + 3) + v7;
              if ( ((unsigned __int8)(*(_BYTE *)(v459 + 20) | *(_BYTE *)(v460 + 20)) & (unsigned __int8)v10) != 0 )
              {
                if ( (*(_WORD *)(v461 + 20) & 0x9000) == 0 )
                {
                  *(_WORD *)(v461 + 20) = v10;
                  goto LABEL_838;
                }
                vdbeMemClearExternAndSetNull(v461);
                goto LABEL_421;
              }
              v468 = sqlite3VdbeIntValue(v460);
              v469 = sqlite3VdbeIntValue(v459);
              v470 = *v6;
              v471 = v469;
              if ( *v6 == 102 )
              {
                v468 &= v469;
LABEL_900:
                v3 = 0;
LABEL_915:
                *(_QWORD *)v461 = v468;
                *(_WORD *)(v461 + 20) &= 0xF244u;
                *(_WORD *)(v461 + 20) |= 4u;
LABEL_949:
                v7 = v826;
LABEL_950:
                v9 = v822;
                goto LABEL_951;
              }
              if ( v470 == 103 )
              {
                v468 |= v469;
                goto LABEL_900;
              }
              v3 = 0;
              if ( !v469 )
                goto LABEL_915;
              if ( v469 < 0 )
              {
                v470 = -47 - v470;
                if ( v469 <= -64 )
                  goto LABEL_906;
                v471 = -v469;
              }
              if ( v471 < 64 )
              {
                if ( v470 == 104 )
                {
                  v468 <<= v471;
                }
                else if ( v468 >= 0 )
                {
                  v468 = (unsigned __int64)v468 >> v471;
                }
                else
                {
                  v468 = ((unsigned __int64)v468 >> v471) | (-1LL << (64 - (unsigned __int8)v471));
                }
                goto LABEL_915;
              }
LABEL_906:
              if ( v468 >= 0 || v470 == 104 )
                v468 = 0;
              else
                v468 = -1;
              goto LABEL_915;
            }
            v462 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( v462 && *(_DWORD *)(v462 + 68) == *((_DWORD *)v6 + 2) )
            {
              v463 = *(_QWORD *)(v462 + 48);
              sqlite3_free(*(_QWORD *)(v463 + 24));
              v3 = 0;
              *(_QWORD *)(v463 + 24) = 0;
              v10 = 1;
              *(_BYTE *)v463 = 1;
LABEL_1026:
              *(_BYTE *)(*(_QWORD *)(v462 + 48) + 3LL) = v6[2] & 3;
              goto LABEL_173;
            }
            goto LABEL_1013;
          }
          if ( (unsigned int)v15 > 0x6F )
          {
            v505 = v15 - 112;
            if ( v505 )
            {
              v506 = v505 - 1;
              if ( v506 )
              {
                v507 = v506 - 1;
                if ( !v507 )
                {
                  v511 = v7 + 56LL * *((int *)v6 + 1);
                  v512 = v7 + 56LL * *((int *)v6 + 2);
                  if ( (*(_WORD *)(v512 + 20) & 0x9000) != 0 )
                  {
                    vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 2));
                    v13 = v823;
                    v3 = 0;
                    v10 = 1;
                  }
                  else
                  {
                    *(_WORD *)(v512 + 20) = v10;
                  }
                  if ( ((unsigned __int8)v10 & *(_BYTE *)(v511 + 20)) == 0 )
                  {
                    *(_WORD *)(v512 + 20) = 4;
                    *(_QWORD *)v512 = ~sqlite3VdbeIntValue(v511);
                    goto LABEL_422;
                  }
                  goto LABEL_623;
                }
                if ( v507 != 1 )
                  goto LABEL_53;
                v508 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2));
                Cursor = allocateCursor(v4, *((unsigned int *)v6 + 1), (unsigned int)*(__int16 *)(v508 + 72), 0);
                if ( Cursor )
                {
                  *(_DWORD *)(Cursor + 8) |= 1u;
                  *(_BYTE *)(Cursor + 2) = 1;
                  *(_QWORD *)(Cursor + 56) = *(_QWORD *)(v508 + 56);
                  *(_BYTE *)(Cursor + 4) = *(_BYTE *)(v508 + 4);
                  *(_DWORD *)(Cursor + 68) = *(_DWORD *)(v508 + 68);
                  v510 = *(_DWORD *)(Cursor + 8) ^ (*(_DWORD *)(v508 + 8) ^ *(_DWORD *)(Cursor + 8)) & 4;
                  *(_DWORD *)(Cursor + 8) = v510;
                  *(_QWORD *)(Cursor + 16) = *(_QWORD *)(v508 + 16);
                  *(_DWORD *)(Cursor + 8) = v510 | 8;
                  *(_DWORD *)(v508 + 8) |= 8u;
                  v14 = sqlite3BtreeCursor(
                          *(_QWORD *)(Cursor + 16),
                          *(_DWORD *)(Cursor + 68),
                          4,
                          *(_QWORD *)(Cursor + 56),
                          *(_QWORD *)(Cursor + 48));
                  Table = v14;
                  goto LABEL_244;
                }
                goto LABEL_1543;
              }
            }
LABEL_1013:
            if ( (v4[25] & 3) == (_BYTE)v10 )
            {
              v14 = 516;
              goto LABEL_1546;
            }
            v513 = *((_DWORD *)v6 + 3);
            v514 = *(_QWORD *)(v2 + 32);
            v515 = *((unsigned int *)v6 + 2);
            v516 = 32LL * v513;
            v517 = *(_QWORD *)(v516 + v514 + 8);
            if ( *v6 == 113 )
            {
              v518 = *((_WORD *)v6 + 1) & 8 | 4;
              v519 = *(_BYTE *)(*(_QWORD *)(v516 + v514 + 24) + 112LL);
              if ( v519 < *((_BYTE *)a1 + 197) )
                *((_BYTE *)a1 + 197) = v519;
            }
            else
            {
              v518 = 0;
            }
            if ( (v6[2] & 0x10) != 0 )
            {
              sqlite3VdbeMemIntegerify(v826 + 56 * v515);
              LODWORD(v515) = *(_DWORD *)(v826 + 56 * v515);
            }
            v520 = v6[1];
            if ( v520 == 0xF8 )
            {
              v521 = *((_QWORD *)v6 + 2);
              v522 = *(unsigned __int16 *)(v521 + 8);
            }
            else
            {
              v522 = 0;
              v521 = 0;
              if ( v520 == 0xFD )
                v522 = *((unsigned int *)v6 + 4);
            }
            v523 = allocateCursor(a1, *((unsigned int *)v6 + 1), v522, 0);
            v462 = v523;
            if ( v523 )
            {
              v524 = *(_QWORD *)(v523 + 48);
              *(_DWORD *)(v523 + 8) |= 4u;
              *(_BYTE *)(v523 + 1) = v513;
              *(_BYTE *)(v523 + 2) = 1;
              *(_DWORD *)(v523 + 68) = v515;
              v525 = sqlite3BtreeCursor(v517, v515, v518, v521, v524);
              v4 = a1;
              v14 = v525;
              v7 = v826;
              *(_QWORD *)(v462 + 56) = v521;
              Table = v525;
              v3 = 0;
              *(_BYTE *)(v462 + 4) = v6[1] != 0xF8;
              v10 = 1;
              goto LABEL_1026;
            }
LABEL_1541:
            v4 = a1;
            goto LABEL_1542;
          }
          if ( (_DWORD)v15 != 111 )
          {
            v472 = v15 - 106;
            if ( v472 )
            {
              v473 = v472 - 1;
              if ( v473 )
              {
                v474 = v473 - 1;
                if ( v474 )
                {
                  if ( (unsigned int)(v474 - 1) > 1 )
                    goto LABEL_53;
                }
              }
            }
            v475 = *((int *)v6 + 3);
            v476 = v7 + 56LL * *((int *)v6 + 1);
            v477 = 56LL * *((int *)v6 + 2) + v7;
            v841 = 0;
            v478 = v826 + 56 * v475;
            v479 = *(_WORD *)(v477 + 20);
            if ( (*(_BYTE *)(v476 + 20) & (unsigned __int8)v479 & 4) == 0 )
            {
              if ( ((unsigned __int8)(*(_BYTE *)(v476 + 20) | v479) & (unsigned __int8)v10) != 0 )
              {
LABEL_973:
                if ( (*(_WORD *)(v478 + 20) & 0x9000) == 0 )
                {
                  v10 = 1;
                  *(_WORD *)(v478 + 20) = 1;
LABEL_976:
                  v13 = v823;
                  goto LABEL_977;
                }
                vdbeMemClearExternAndSetNull(v478);
LABEL_854:
                v4 = a1;
                goto LABEL_421;
              }
              v480 = numericType(v476);
              if ( (v480 & (unsigned __int8)numericType(v477) & 4) == 0 )
                goto LABEL_955;
              v3 = 0;
              v10 = 1;
            }
            v481 = *v6;
            v482 = *(_QWORD *)v477;
            v483 = *(_QWORD *)v476;
            v841 = *(_QWORD *)v477;
            v484 = v481 - 106;
            if ( !v484 )
            {
              if ( v483 < 0 )
              {
                if ( v482 < 0 && (__int64)(0x8000000000000001uLL - v482) > v483 + 1 )
                  goto LABEL_955;
              }
              else if ( v482 > 0 && 0x7FFFFFFFFFFFFFFFLL - v482 < v483 )
              {
                goto LABEL_955;
              }
              v488 = v482 + v483;
              goto LABEL_946;
            }
            v485 = v484 - 1;
            if ( v485 )
            {
              v486 = v485 - 1;
              if ( v486 )
              {
                if ( v486 != 1 )
                {
                  if ( v483 )
                  {
                    v487 = v482;
                    if ( v483 == -1 )
                      v483 = v10;
                    v841 = v487 % v483;
                    goto LABEL_947;
                  }
                  goto LABEL_972;
                }
                if ( !v483 )
                  goto LABEL_972;
                if ( v483 != -1 || v482 != 0x8000000000000000uLL )
                {
                  v488 = v482 / v483;
LABEL_946:
                  v841 = v488;
LABEL_947:
                  *(_QWORD *)v478 = v841;
                  v490 = *(_WORD *)(v478 + 20) & 0xF240 | 4;
LABEL_948:
                  *(_WORD *)(v478 + 20) = v490;
                  v4 = a1;
                  goto LABEL_949;
                }
LABEL_955:
                v491 = sqlite3VdbeRealValue(v476);
                v492 = sqlite3VdbeRealValue(v477);
                switch ( *v6 )
                {
                  case 'j':
                    v495 = v492 + v491;
                    break;
                  case 'k':
                    v495 = v492 - v491;
                    break;
                  case 'l':
                    v495 = v492 * v491;
                    break;
                  case 'm':
                    if ( v491 == 0.0 )
                    {
                      v3 = 0;
                      goto LABEL_972;
                    }
                    v495 = v492 / v491;
                    break;
                  default:
                    v493 = sqlite3VdbeIntValue(v476);
                    v494 = sqlite3VdbeIntValue(v477);
                    v3 = 0;
                    v841 = v494;
                    if ( v493 )
                    {
                      if ( v493 == -1 )
                        v493 = 1;
                      v495 = (double)(int)(v494 % v493);
LABEL_969:
                      if ( (*(_QWORD *)&v495 & 0xFFFFFFFFFFFFFLL) == 0
                        || (*(_QWORD *)&v495 & 0x7FF0000000000000LL) != 0x7FF0000000000000LL )
                      {
                        v496 = *(_WORD *)(v478 + 20);
                        *(double *)v478 = v495;
                        v490 = v496 & 0xF240 | 8;
                        goto LABEL_948;
                      }
                    }
LABEL_972:
                    v5 = v825;
                    goto LABEL_973;
                }
                v3 = 0;
                goto LABEL_969;
              }
              v489 = sqlite3MulInt64(&v841, v483);
            }
            else
            {
              v489 = sqlite3SubInt64(&v841, v483);
            }
            v3 = 0;
            if ( !v489 )
              goto LABEL_947;
            goto LABEL_955;
          }
          v497 = v7 + 56LL * *((int *)v6 + 1);
          v498 = *(_WORD *)(v497 + 20);
          v499 = v7 + 56LL * *((int *)v6 + 2);
          v500 = v7 + 56LL * *((int *)v6 + 3);
          if ( ((unsigned __int8)(*(_BYTE *)(v499 + 20) | v498) & (unsigned __int8)v10) != 0 )
          {
            if ( (*(_WORD *)(v500 + 20) & 0x9000) == 0 )
            {
              v14 = Table;
              *(_WORD *)(v500 + 20) = v10;
              goto LABEL_148;
            }
            v433 = v7 + 56LL * *((int *)v6 + 3);
            goto LABEL_803;
          }
          if ( (v498 & 0x12) != 0 )
          {
            if ( (v498 & 0x400) == 0 )
              goto LABEL_989;
            v501 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 1));
          }
          else
          {
            LOBYTE(v13) = v822;
            v501 = sqlite3VdbeMemStringify(v7 + 56LL * *((int *)v6 + 1), v13, 0);
          }
          if ( v501 )
            goto LABEL_1542;
          v498 = *(_WORD *)(v497 + 20) & 0xFFFD;
LABEL_989:
          v502 = *(_WORD *)(v499 + 20);
          if ( (v502 & 0x12) != 0 )
          {
            if ( (v502 & 0x400) == 0 )
              goto LABEL_995;
            v503 = sqlite3VdbeMemExpandBlob(v499);
          }
          else
          {
            LOBYTE(v13) = v822;
            v503 = sqlite3VdbeMemStringify(v499, v13, 0);
          }
          if ( !v503 )
          {
            v502 = *(_WORD *)(v499 + 20) & 0xFFFD;
LABEL_995:
            LODWORD(v504) = *(_DWORD *)(v497 + 16) + *(_DWORD *)(v499 + 16);
            if ( (int)v504 > *(_DWORD *)(v830 + 136) )
              goto LABEL_1527;
            if ( !(unsigned int)sqlite3VdbeMemGrow(v500, (unsigned int)(v504 + 2), v500 == v499) )
            {
              v504 = (int)v504;
              *(_WORD *)(v500 + 20) &= 0xF242u;
              *(_WORD *)(v500 + 20) |= 2u;
              if ( v500 != v499 )
              {
                memcpy_0(*(void **)(v500 + 8), *(const void **)(v499 + 8), *(int *)(v499 + 16));
                *(_WORD *)(v499 + 20) = v502;
              }
              memcpy_0(
                (void *)(*(_QWORD *)(v500 + 8) + *(int *)(v499 + 16)),
                *(const void **)(v497 + 8),
                *(int *)(v497 + 16));
              v9 = v822;
              v10 = 1;
              *(_WORD *)(v497 + 20) = v498;
              if ( v822 > 1u )
                v504 = (int)v504 & 0xFFFFFFFFFFFFFFFEuLL;
              v3 = 0;
              v14 = Table;
              *(_BYTE *)(v504 + *(_QWORD *)(v500 + 8)) = 0;
              *(_BYTE *)(*(_QWORD *)(v500 + 8) + v504 + 1) = 0;
              *(_WORD *)(v500 + 20) |= 0x200u;
              *(_DWORD *)(v500 + 16) = v504;
              v4 = a1;
              *(_BYTE *)(v500 + 22) = v822;
              goto LABEL_335;
            }
            goto LABEL_1541;
          }
LABEL_1542:
          v2 = v830;
          goto LABEL_1543;
        }
LABEL_1042:
        if ( *((int *)v6 + 3) > 0 )
        {
          *(_DWORD *)(56LL * *((int *)v6 + 3) + v7 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v6 + 3) + v7 + 8) = &Src;
        }
        v534 = *((int *)v6 + 1);
        v535 = *(_QWORD *)(v4[15] + 8 * v534);
        if ( !v535 || (*(_BYTE *)(v535 + 8) & 8) != 0 || *((_DWORD *)v6 + 2) > *(__int16 *)(v535 + 72) )
        {
          v539 = allocateCursor(v4, v534, *((unsigned int *)v6 + 2), 0);
          v535 = v539;
          if ( !v539 )
            goto LABEL_1543;
          v540 = (_QWORD *)(v539 + 16);
          *(_DWORD *)(v539 + 8) |= 1u;
          LODWORD(v821) = *((unsigned __int16 *)v6 + 1) | 5;
          v541 = sqlite3BtreeOpen(*(_QWORD *)v2, 0, v2, v539 + 16, v821, 1054);
          v3 = 0;
          v14 = v541;
          if ( v541 )
            goto LABEL_1545;
          v542 = sqlite3BtreeBeginTrans(*v540, 1, 0);
          v3 = 0;
          Table = v542;
          v14 = v542;
          if ( !v542 )
          {
            v543 = *((_QWORD *)v6 + 2);
            v544 = (_DWORD *)(v535 + 68);
            *(_QWORD *)(v535 + 56) = v543;
            if ( v543 )
            {
              v545 = *v540;
              v546 = *((unsigned __int16 *)v6 + 1) | 2;
              sqlite3BtreeEnter(*v540);
              Table = btreeCreateTable(v545, v535 + 68, v546);
              sqlite3BtreeLeave(v545);
              v3 = 0;
              if ( Table )
              {
                v14 = Table;
              }
              else
              {
                v14 = sqlite3BtreeCursor(*v540, *v544, 4, v543, *(_QWORD *)(v535 + 48));
                Table = v14;
                v3 = 0;
              }
              v9 = v822;
              *(_BYTE *)(v535 + 4) = 0;
            }
            else
            {
              v547 = *(_QWORD *)(v535 + 48);
              v548 = *v540;
              *v544 = 1;
              v14 = sqlite3BtreeCursor(v548, 1, 4, 0, v547);
              Table = v14;
              v3 = 0;
              *(_BYTE *)(v535 + 4) = 1;
            }
          }
          *(_DWORD *)(v535 + 8) = *(_DWORD *)(v535 + 8) & 0xFFFFFFFB | (*((_WORD *)v6 + 1) != 8 ? 4 : 0);
          if ( v14 )
          {
            sqlite3BtreeClose(*(_QWORD *)(v535 + 16));
            goto LABEL_1522;
          }
          v4 = a1;
        }
        else
        {
          v536 = *(unsigned int *)(v535 + 68);
          v537 = *(_QWORD *)(v535 + 16);
          *(_QWORD *)(v535 + 24) = 0;
          *(_DWORD *)(v535 + 32) = 0;
          v538 = sqlite3BtreeClearTable(v537, v536, 0);
          v3 = 0;
          Table = v538;
          v14 = v538;
          if ( v538 )
            goto LABEL_1546;
        }
        v10 = 1;
        *(_BYTE *)(v535 + 2) = 1;
        goto LABEL_335;
      }
      if ( (unsigned int)v15 <= 0x81 )
      {
        if ( (_DWORD)v15 == 129 )
        {
          if ( *((_DWORD *)v6 + 3) )
            v595 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
          else
            v595 = 0;
          v71 = sqlite3BtreeTransferRow(
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL),
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2)) + 48LL),
                  v595);
          goto LABEL_153;
        }
        if ( (unsigned int)v15 <= 0x7A )
        {
          if ( (_DWORD)v15 == 122 )
          {
            if ( *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) )
            {
              sqlite3VdbeFreeCursorNN(v4);
              v5 = v825;
              v3 = 0;
              v10 = 1;
            }
            *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) = 0;
            goto LABEL_196;
          }
          v526 = v15 - 117;
          if ( !v526 )
          {
            v549 = out2Prerelease(v4, v6);
            v551 = *((_QWORD *)v6 + 2);
            v552 = v549;
            if ( v551 )
            {
              v554 = -1;
              do
                ++v554;
              while ( *(_BYTE *)(v551 + v554) );
              v553 = v554 & 0x3FFFFFFF;
            }
            else
            {
              v553 = 0;
            }
            *((_DWORD *)v6 + 1) = v553;
            if ( v9 != 1 )
            {
              LOBYTE(v550) = 1;
              Table = sqlite3VdbeMemSetStr(v549, v551, -1, v550, 0);
              v14 = Table;
              if ( Table )
                goto LABEL_1528;
              if ( (unsigned int)sqlite3VdbeChangeEncoding(v552, v9) )
                goto LABEL_1543;
              *(_DWORD *)(v552 + 32) = 0;
              *(_WORD *)(v552 + 20) |= 0x2000u;
              if ( v6[1] == 0xFA && *((_QWORD *)v6 + 2) )
                sqlite3DbFreeNN(v2);
              v6[1] = -6;
              *((_QWORD *)v6 + 2) = *(_QWORD *)(v552 + 8);
              v553 = *(_DWORD *)(v552 + 16);
              *((_DWORD *)v6 + 1) = v553;
            }
            if ( v553 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            *v6 = 73;
LABEL_1075:
            v555 = out2Prerelease(v4, v6);
            v3 = 0;
            *(_WORD *)(v555 + 20) = 8706;
            *(_QWORD *)(v555 + 8) = *((_QWORD *)v6 + 2);
            *(_DWORD *)(v555 + 16) = *((_DWORD *)v6 + 1);
            *(_BYTE *)(v555 + 22) = v9;
            if ( *((int *)v6 + 3) <= 0 )
            {
LABEL_1408:
              v10 = 1;
              goto LABEL_1404;
            }
            v10 = 1;
            v13 = v823;
            if ( *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) == *((unsigned __int16 *)v6 + 1) )
            {
              *(_WORD *)(v555 + 20) = 8720;
              goto LABEL_1078;
            }
            goto LABEL_623;
          }
          v527 = v526 - 1;
          if ( v527 )
          {
            v528 = v527 - 1;
            if ( v528 )
            {
              v529 = v528 - 1;
              if ( v529 )
              {
                if ( v529 != 1 )
                  goto LABEL_53;
                LOBYTE(v16) = 3;
                v530 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 3), v16);
                v3 = 0;
                if ( !v530 )
                  goto LABEL_1543;
                v10 = 1;
                *(_BYTE *)(v530 + 2) = 1;
                *(_DWORD *)(v530 + 36) = *((_DWORD *)v6 + 2);
                *(_QWORD *)(v530 + 48) = &dword_18010F964;
                *(_BYTE *)(v530 + 4) = 1;
                goto LABEL_195;
              }
              v531 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
              v532 = *(_QWORD *)(v531 + 24);
              *(_QWORD *)(v531 + 24) = v532 + 1;
              if ( v532 )
                goto LABEL_196;
              goto LABEL_1219;
            }
            LOBYTE(v16) = v10;
            v533 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 2), v16);
            if ( !v533 )
              goto LABEL_1543;
            *(_QWORD *)(v533 + 56) = *((_QWORD *)v6 + 2);
            v71 = sqlite3VdbeSorterInit(v2, *((unsigned int *)v6 + 3), v533);
            goto LABEL_153;
          }
          goto LABEL_1042;
        }
        v556 = v15 - 124;
        if ( !v556 )
        {
          v586 = *((int *)v6 + 7);
          *(_QWORD *)&v837 = 0;
          v587 = v4[15];
          LODWORD(v829) = 0;
          v835 = 0;
          v836 = 0;
          v588 = *(_QWORD *)(v587 + 8 * v586);
          if ( **(_BYTE **)(v588 + 48) )
            goto LABEL_53;
          v589 = *((_DWORD *)v6 + 1);
          *(_QWORD *)&v835 = *(_QWORD *)(v588 + 56);
          WORD6(v836) = *((_WORD *)v6 + 20);
          v590 = *((int *)v6 + 9);
          BYTE14(v836) = 0;
          *((_QWORD *)&v835 + 1) = v7 + 56 * v590;
          while ( 1 )
          {
            v591 = sqlite3VdbeIdxKeyCompare(v2, v588, &v835, &v829);
            v3 = 0;
            Table = v591;
            v14 = v591;
            if ( v591 )
              goto LABEL_1546;
            v592 = (int)v829 < 0;
            if ( (int)v829 > 0 )
            {
              if ( !*((_WORD *)v6 + 1) )
                goto LABEL_1149;
              v592 = (int)v829 < 0;
            }
            if ( !v592 )
              goto LABEL_1218;
            if ( v589 <= 0 )
              goto LABEL_1408;
            v593 = *(_QWORD *)(v588 + 48);
            *(_DWORD *)(v588 + 32) = 0;
            v594 = sqlite3BtreeNext(v593, 0);
            v3 = 0;
            v14 = v594;
            if ( v594 )
              break;
            --v589;
          }
          if ( v594 != 101 )
            goto LABEL_1546;
          v14 = 0;
          Table = 0;
LABEL_1149:
          v9 = v822;
          v6 += 24;
          goto LABEL_213;
        }
        v557 = v556 - 1;
        if ( !v557 )
        {
          v584 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v585 = *(unsigned __int16 *)(v584 + 12);
          if ( v585 >= *((_DWORD *)v6 + 2) )
          {
            if ( v585 > *((_DWORD *)v6 + 3) )
              *(_WORD *)(v584 + 12) = *((_WORD *)v6 + 6);
            v13 = v823;
            goto LABEL_53;
          }
          *(_WORD *)(v584 + 12) = *((_WORD *)v6 + 4);
LABEL_196:
          v13 = v823;
          goto LABEL_53;
        }
        v558 = v557 - 1;
        if ( !v558 )
        {
          v582 = (_QWORD *)out2Prerelease(v4, v6);
          v10 = 1;
          *v582 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 24LL);
          v583 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          ++*(_QWORD *)(v583 + 24);
          goto LABEL_60;
        }
        v559 = v558 - 1;
        if ( !v559 )
        {
          v829 = 0;
          LODWORD(v831) = 0;
          v573 = (__int64 *)out2Prerelease(v4, v6);
          v574 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( (*(_BYTE *)(v574 + 8) & 2) != 0 )
          {
            v3 = 0;
          }
          else
          {
            v575 = sqlite3BtreeLast(*(_QWORD *)(v574 + 48), &v831);
            v3 = 0;
            Table = v575;
            v14 = v575;
            if ( v575 )
              goto LABEL_1546;
            if ( (_DWORD)v831 )
            {
              v829 = 1;
            }
            else
            {
              v576 = sqlite3BtreeIntegerKey(*(_QWORD *)(v574 + 48));
              v829 = v576;
              if ( v576 == 0x7FFFFFFFFFFFFFFFLL )
                *(_DWORD *)(v574 + 8) |= 2u;
              else
                v829 = v576 + 1;
              v3 = 0;
            }
          }
          if ( *((_DWORD *)v6 + 3) )
          {
            v577 = v4[33];
            if ( v577 )
            {
              while ( *(_QWORD *)(v577 + 8) )
                v577 = *(_QWORD *)(v577 + 8);
              v578 = (__int64 *)(*(_QWORD *)(v577 + 24) + 56LL * *((int *)v6 + 3));
            }
            else
            {
              v578 = (__int64 *)(v826 + 56LL * *((int *)v6 + 3));
            }
            sqlite3VdbeMemIntegerify(v578);
            if ( *v578 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v574 + 8) & 2) != 0 )
            {
              v14 = 13;
              goto LABEL_1523;
            }
            v579 = v829;
            if ( v829 < *v578 + 1 )
            {
              v579 = *v578 + 1;
              v829 = v579;
            }
            *v578 = v579;
            v3 = 0;
          }
          if ( (*(_BYTE *)(v574 + 8) & 2) != 0 )
          {
            v580 = 0;
            while ( 1 )
            {
              sqlite3_randomness(8, &v829);
              v829 = (v829 & 0x3FFFFFFFFFFFFFFFLL) + 1;
              v581 = sqlite3BtreeTableMoveto(*(_QWORD *)(v574 + 48), v829, 0, &v831);
              v3 = 0;
              Table = v581;
              v14 = v581;
              if ( v581 )
                goto LABEL_1546;
              if ( (_DWORD)v831 )
                break;
              if ( ++v580 >= 100 )
              {
                v14 = 13;
                goto LABEL_1546;
              }
            }
          }
          *(_BYTE *)(v574 + 3) = 0;
          *(_DWORD *)(v574 + 32) = 0;
          *v573 = v829;
          goto LABEL_79;
        }
        if ( v559 != 1 )
          goto LABEL_53;
        v560 = *((int *)v6 + 1);
        v561 = 56LL * *((int *)v6 + 2);
        v835 = 0;
        v836 = 0;
        v562 = v4[15];
        v837 = 0;
        v563 = *(_QWORD *)(v562 + 8 * v560);
        v72 = v6[1] == 0xFB;
        v564 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
        *((_QWORD *)&v835 + 1) = v564;
        if ( v72 && *(_QWORD *)(v2 + 320) )
        {
          v565 = *((_QWORD *)v6 + 2);
          v566 = *(_QWORD *)(32LL * *(char *)(v563 + 1) + *(_QWORD *)(v2 + 32));
        }
        else
        {
          v565 = 0;
          v566 = 0;
        }
        if ( ((unsigned __int8)v10 & v6[2]) != 0 )
        {
          v4[7] += v10;
          if ( (v6[2] & 0x20) != 0 )
            *(_QWORD *)(v2 + 56) = v564;
        }
        v567 = *((_WORD *)v6 + 1);
        *(_QWORD *)&v836 = *(_QWORD *)(v561 + v826 + 8);
        DWORD1(v837) = *(_DWORD *)(v561 + v826 + 16);
        if ( (v567 & 0x10) != 0 )
          v568 = *(unsigned int *)(v563 + 36);
        else
          v568 = 0;
        if ( (*(_WORD *)(v561 + v826 + 20) & 0x400) != 0 )
          DWORD2(v837) = *(_DWORD *)(v561 + v826);
        else
          DWORD2(v837) = 0;
        *(_QWORD *)&v835 = 0;
        v569 = sqlite3BtreeInsert(*(_QWORD *)(v563 + 48), &v835, (unsigned __int8)v567 & 0x8A, v568);
        v3 = 0;
        Table = v569;
        *(_BYTE *)(v563 + 3) = 0;
        v14 = v569;
        *(_DWORD *)(v563 + 32) = 0;
        if ( v569 )
          goto LABEL_1546;
        v10 = 1;
        ++v838;
        if ( !v565 )
          goto LABEL_1403;
        v570 = *((_QWORD *)&v835 + 1);
        v571 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64))(v2 + 320);
        v572 = (v6[2] & 4) != 0 ? 23 : 18;
LABEL_1103:
        v571(*(_QWORD *)(v2 + 312), v572, v566, *(_QWORD *)v565, v570);
        goto LABEL_421;
      }
      if ( (unsigned int)v15 > 0x87 )
      {
        switch ( (_DWORD)v15 )
        {
          case 0x88:
            v642 = *((int *)v6 + 1);
            v643 = *(_QWORD *)(v4[15] + 8 * v642);
            if ( !v643 )
            {
              LOBYTE(v16) = 3;
              v643 = allocateCursor(v4, v642, (unsigned int)v10, v16);
              if ( !v643 )
                goto LABEL_1543;
              *(_DWORD *)(v643 + 8) |= 8u;
              *(_DWORD *)(v643 + 36) = 0;
              *(_BYTE *)(v643 + 4) = 1;
              valid = sqlite3BtreeFakeValidCursor();
              v3 = 0;
              *(_QWORD *)(v643 + 48) = valid;
              v10 = 1;
            }
            *(_BYTE *)(v643 + 2) = v10;
            *(_DWORD *)(v643 + 32) = 0;
            if ( !*(_BYTE *)v643 )
            {
              sqlite3BtreeClearCursor(*(_QWORD *)(v643 + 48));
              goto LABEL_244;
            }
            goto LABEL_1404;
          case 0x89:
            goto LABEL_1211;
          case 0x8A:
            v627 = v4[15];
            v628 = *((int *)v6 + 1);
            v835 = 0;
            v836 = 0;
            v837 = 0;
            v629 = *(_QWORD *)(v627 + 8 * v628);
            v630 = v7 + 56LL * *((int *)v6 + 2);
            if ( ((unsigned __int8)v10 & v6[2]) != 0 )
              v4[7] += v10;
            if ( (*(_WORD *)(v630 + 20) & 0x400) != 0 )
            {
              v631 = sqlite3VdbeMemExpandBlob(v630);
              v3 = 0;
              v14 = v631;
              if ( v631 )
                goto LABEL_1546;
            }
            v632 = *((_WORD *)v6 + 1);
            *((_QWORD *)&v835 + 1) = *(int *)(v630 + 16);
            *(_QWORD *)&v835 = *(_QWORD *)(v630 + 8);
            v633 = v7 + 56LL * *((int *)v6 + 3);
            LOWORD(v837) = *((_WORD *)v6 + 8);
            *((_QWORD *)&v836 + 1) = v633;
            if ( (v632 & 0x10) != 0 )
              v634 = *(unsigned int *)(v629 + 36);
            else
              v634 = 0;
            v626 = sqlite3BtreeInsert(*(_QWORD *)(v629 + 48), &v835, (unsigned __int8)v632 & 0x8A, v634);
            v3 = 0;
            *(_DWORD *)(v629 + 32) = 0;
            break;
          default:
            v623 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v624 = v7 + 56LL * *((int *)v6 + 2);
            if ( (*(_WORD *)(v624 + 20) & 0x400) != 0 )
            {
              v625 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              v14 = v625;
              if ( v625 )
                goto LABEL_1546;
            }
            v626 = sqlite3VdbeSorterWrite(v623, v624);
            v3 = 0;
            break;
        }
        Table = v626;
        v14 = v626;
        v170 = v626 == 0;
LABEL_326:
        if ( !v170 )
          goto LABEL_1546;
        goto LABEL_80;
      }
      if ( (_DWORD)v15 != 135 )
      {
        v596 = v15 - 130;
        if ( v596 )
        {
          v597 = v596 - 1;
          if ( !v597 )
          {
            sqlite3VdbeSetChanges(v2, v4[7]);
            v3 = 0;
            v4[7] = 0;
            goto LABEL_52;
          }
          v598 = v597 - 1;
          if ( v598 )
          {
            v599 = v598 - 1;
            if ( !v599 )
            {
              v605 = sqlite3VdbeSorterRowkey(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)), v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              Table = v605;
              v14 = v605;
              if ( v605 )
                goto LABEL_1546;
              *(_DWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3)) + 32LL) = 0;
              goto LABEL_52;
            }
            if ( v599 != 1 )
              goto LABEL_53;
            v600 = out2Prerelease(v4, v6);
            v601 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL);
            v602 = sqlite3BtreePayloadSize(v601);
            if ( v602 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            v603 = sqlite3VdbeMemFromBtreeZeroOffset(v601, v602, v600);
            v3 = 0;
            Table = v603;
            v14 = v603;
            if ( v603 )
              goto LABEL_1546;
            if ( !*((_DWORD *)v6 + 3) && (*(_WORD *)(v600 + 20) & 0x4000) != 0 )
            {
              Writeable = sqlite3VdbeMemMakeWriteable(v600);
              v3 = 0;
              if ( Writeable )
                goto LABEL_1543;
              goto LABEL_80;
            }
            goto LABEL_1408;
          }
          v606 = v4[15];
          v607 = *((unsigned int *)v6 + 4);
          v608 = 56LL * *((int *)v6 + 3);
          v609 = *((int *)v6 + 1);
          LODWORD(v829) = 0;
          v610 = sqlite3VdbeSorterCompare(*(_QWORD *)(v606 + 8 * v609), v7 + v608, v607, &v829);
          v3 = 0;
          Table = v610;
          v14 = v610;
          if ( v610 )
            goto LABEL_1546;
          v105 = (_DWORD)v829 == 0;
          goto LABEL_194;
        }
        v611 = *((_DWORD *)v6 + 2);
        v612 = *(_QWORD *)(a1[15] + 8LL * *((int *)v6 + 1));
        if ( v6[1] == 0xFB && *(_QWORD *)(v2 + 320) )
        {
          v565 = *((_QWORD *)v6 + 2);
          v566 = *(_QWORD *)(32LL * *(char *)(v612 + 1) + *(_QWORD *)(v2 + 32));
          if ( (v6[2] & 2) != 0 && *(_BYTE *)(v612 + 4) )
            *(_QWORD *)(v612 + 80) = sqlite3BtreeIntegerKey(*(_QWORD *)(v612 + 48));
        }
        else
        {
          v566 = 0;
          v565 = 0;
        }
        LOBYTE(v13) = v6[2];
        v613 = sqlite3BtreeDelete(*(_QWORD *)(v612 + 48), v13);
        v3 = 0;
        Table = v613;
        *(_QWORD *)(v612 + 32) = 0;
        v14 = v613;
        if ( v613 )
          goto LABEL_1545;
        v10 = 1;
        ++v838;
        v72 = (v611 & 1) == 0;
        v4 = a1;
        if ( v72 )
          goto LABEL_1403;
        ++a1[7];
        v571 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64))(v2 + 320);
        if ( !v571 || !v565 || *(char *)(v565 + 48) < 0 )
          goto LABEL_1403;
        v570 = *(_QWORD *)(v612 + 80);
        v572 = v14 + 9;
        goto LABEL_1103;
      }
      v839 = 0;
      v614 = out2Prerelease(v4, v6);
      v615 = *((int *)v6 + 1);
      v3 = 0;
      v616 = v4[15];
      v617 = v614;
      v618 = *(_QWORD *)(v616 + 8 * v615);
      if ( *(_BYTE *)(v618 + 2) )
      {
        v10 = 1;
        *(_WORD *)(v614 + 20) = 1;
        goto LABEL_146;
      }
      if ( *(_BYTE *)(v618 + 3) )
      {
        v619 = *(_QWORD *)(v618 + 80);
      }
      else if ( *(_BYTE *)v618 == 2 )
      {
        v620 = *(__int64 **)(v618 + 48);
        v621 = *v620;
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*(_QWORD *)*v620 + 96LL))(v620, &v839);
        v14 = Table;
        sqlite3VtabImportErrmsg(v4, v621);
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        v619 = v839;
      }
      else
      {
        v622 = sqlite3VdbeCursorRestore(*(_QWORD *)(v616 + 8 * v615));
        v3 = 0;
        Table = v622;
        v14 = v622;
        if ( v622 )
          goto LABEL_1546;
        if ( *(_BYTE *)(v618 + 2) )
        {
          v10 = 1;
          *(_WORD *)(v617 + 20) = 1;
          goto LABEL_146;
        }
        v619 = sqlite3BtreeIntegerKey(*(_QWORD *)(v618 + 48));
        v3 = 0;
      }
LABEL_1195:
      *(_QWORD *)v617 = v619;
      goto LABEL_80;
    }
    if ( (unsigned int)v15 > 0xA3 )
    {
      if ( (unsigned int)v15 <= 0xAE )
      {
        if ( (_DWORD)v15 == 174 )
        {
          v757 = *((int *)v6 + 2);
          v828 = 0;
          v758 = v7 + 56 * v757;
          sqlite3VdbeMemSetNull(v758);
          v759 = (_QWORD *)*((_QWORD *)v6 + 2);
          v3 = 0;
          v760 = v759[10];
          if ( !v760 )
            goto LABEL_1406;
          v761 = *(__int64 **)(v760 + 16);
          v762 = *v761;
          sqlite3VtabLock();
          v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, unsigned int **))(v762 + 192))(
                  v761,
                  *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32)),
                  *v759,
                  *((unsigned int *)v6 + 3),
                  &v828);
          Table = v14;
          sqlite3VtabUnlock(v759[10]);
          v3 = 0;
          if ( v14 )
          {
            sqlite3_free(v828);
            goto LABEL_1522;
          }
          if ( !v828 )
          {
LABEL_1406:
            v4 = a1;
LABEL_1407:
            v7 = v826;
            goto LABEL_1408;
          }
          LOBYTE(v763) = 1;
          sqlite3VdbeMemSetStr(v758, v828, -1, v763, sqlite3_free);
          goto LABEL_854;
        }
        if ( (unsigned int)v15 <= 0xA9 )
        {
          if ( (_DWORD)v15 != 169 )
          {
            v739 = v15 - 164;
            if ( v739 )
            {
              v740 = v739 - 1;
              if ( v740 )
              {
                v741 = v740 - 1;
                if ( v741 )
                {
                  v742 = v741 - 1;
                  if ( v742 )
                  {
                    if ( v742 != 1 )
                      goto LABEL_53;
                    sqlite3BtreeCursorUnpin(*(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL));
                  }
                  else
                  {
                    sqlite3BtreeCursorPin(*(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL));
                  }
                }
                else
                {
                  if ( *((_DWORD *)v6 + 1) )
                  {
                    *((_DWORD *)v4 + 50) ^= ((unsigned __int8)*((_DWORD *)v4 + 50)
                                           ^ (unsigned __int8)(v10 + *((_DWORD *)v6 + 2)))
                                          & 3;
                    goto LABEL_53;
                  }
                  sqlite3ExpirePreparedStatements(v2, *((unsigned int *)v6 + 2));
                }
                goto LABEL_244;
              }
            }
            v743 = v7 + 56LL * *((int *)v6 + 1);
            if ( *((_DWORD *)v6 + 3) )
            {
              v14 = sqlite3VdbeMemAggValue(v743, v7 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2));
              Table = v14;
              v743 = v7 + 56LL * *((int *)v6 + 3);
            }
            else
            {
              v14 = sqlite3VdbeMemFinalize(v743, *((_QWORD *)v6 + 2));
              Table = v14;
            }
            if ( !v14 )
            {
              sqlite3VdbeChangeEncoding(v743, v9);
              goto LABEL_244;
            }
            v805 = (const char *)sqlite3_value_text(v743);
            v806 = "%s";
            goto LABEL_1538;
          }
          if ( v6[12] || (*(_QWORD *)(v2 + 48) & 0x400000000LL) == 0 )
          {
            v744 = sqlite3BtreeLockTable(
                     *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8),
                     *((unsigned int *)v6 + 2));
            v3 = 0;
            Table = v744;
            v14 = v744;
            if ( v744 )
            {
              if ( (_BYTE)v744 != 6 )
                goto LABEL_1546;
              sqlite3VdbeError(v4, "database table is locked: %s", *((_QWORD *)v6 + 2));
              goto LABEL_1523;
            }
            goto LABEL_52;
          }
          goto LABEL_1078;
        }
        v745 = v15 - 170;
        if ( v745 )
        {
          v746 = v745 - 1;
          if ( v746 )
          {
            v747 = v746 - 1;
            if ( v747 )
            {
              if ( v747 != 1 )
                goto LABEL_53;
              v748 = *((_QWORD *)v6 + 2);
              v828 = 0;
              v749 = *(__int64 **)(v748 + 16);
              if ( v749 )
              {
                v750 = *v749;
                if ( *v749 )
                {
                  Table = (*(__int64 (__fastcall **)(__int64 *, unsigned int **))(v750 + 48))(v749, &v828);
                  v14 = Table;
                  sqlite3VtabImportErrmsg(v4, v749);
                  v3 = 0;
                  if ( Table )
                    goto LABEL_1546;
                  LOBYTE(v751) = 2;
                  *(_QWORD *)v828 = v749;
                  v752 = allocateCursor(v4, *((unsigned int *)v6 + 1), 0, v751);
                  v3 = 0;
                  if ( v752 )
                  {
                    v10 = 1;
                    *(_QWORD *)(v752 + 48) = v828;
                    ++*((_DWORD *)v749 + 2);
                    goto LABEL_146;
                  }
                  (*(void (__fastcall **)(unsigned int *))(v750 + 56))(v828);
                  goto LABEL_1543;
                }
              }
              goto LABEL_1504;
            }
            *(_DWORD *)(v2 + 232) += v10;
            v71 = sqlite3VtabCallDestroy(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
            --*(_DWORD *)(v2 + 232);
            goto LABEL_153;
          }
          v847 = 0;
          v753 = *((int *)v6 + 2);
          *(_QWORD *)&v845 = 0;
          v844 = 0;
          v846 = 0;
          *((_QWORD *)&v845 + 1) = v2;
          Table = sqlite3VdbeMemCopy(&v844, v7 + 56 * v753);
          v14 = Table;
          v754 = sqlite3_value_text(&v844);
          if ( v754 )
          {
            v14 = sqlite3VtabCallCreate(v2, *((unsigned int *)v6 + 1), v754, v4 + 21);
            Table = v14;
          }
          sqlite3VdbeMemRelease(&v844);
        }
        else
        {
          v755 = *((_QWORD *)v6 + 2);
          v756 = sqlite3VtabBegin(v2, v755);
          v3 = 0;
          Table = v756;
          v14 = v756;
          if ( !v755 )
            goto LABEL_1246;
          sqlite3VtabImportErrmsg(v4, *(_QWORD *)(v755 + 16));
        }
        v3 = 0;
LABEL_1246:
        v72 = v14 == 0;
LABEL_154:
        if ( !v72 )
          goto LABEL_1546;
        goto LABEL_52;
      }
      if ( (unsigned int)v15 <= 0xB4 )
      {
        if ( (_DWORD)v15 == 180 )
        {
          *(_WORD *)(56LL * *((int *)v6 + 1) + v7 + 20) &= ~0x800u;
          goto LABEL_53;
        }
        v764 = v15 - 175;
        if ( !v764 )
        {
          v785 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v786 = (_QWORD *)sqlite3_malloc64(16);
          v787 = v786;
          if ( v786 )
          {
            *v786 = *(_QWORD *)(v785 + 48);
            v786[1] = v7 + 56LL * *((int *)v6 + 3);
            v788 = out2Prerelease(v4, v6);
            *(_WORD *)(v788 + 20) = 1;
            sqlite3VdbeMemSetPointer(v788, v787, "ValueList", sqlite3VdbeValueListFree);
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        v765 = v764 - 1;
        if ( !v765 )
        {
          v854 = 0;
          v856 = 0;
          memset(v852, 0, sizeof(v852));
          v857 = 0;
          v853 = 0;
          memset_0(&v855, 0, 0x45u);
          v777 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v778 = *((int *)v6 + 3);
          v779 = v7 + 56 * v778;
          if ( *(_BYTE *)(v777 + 2) )
          {
            sqlite3VdbeMemSetNull(v7 + 56 * v778);
            goto LABEL_422;
          }
          v780 = **(__int64 ***)(v777 + 48);
          v781 = *v780;
          BYTE8(v853) = v822;
          *((_QWORD *)&v852[0] + 1) = &v855;
          *(_QWORD *)&v852[0] = v779;
          v858 = 0x1000000;
          if ( (v6[2] & 1) != 0 )
          {
            sqlite3VdbeMemSetNull(v779);
            v782 = 1025;
            *(_DWORD *)v779 = 0;
          }
          else
          {
            v782 = *(_WORD *)(v779 + 20) & 0xF240 | 1;
          }
          *(_WORD *)(v779 + 20) = v782;
          v783 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v781 + 88))(
                   *(_QWORD *)(v777 + 48),
                   v852,
                   *((unsigned int *)v6 + 2));
          v4 = a1;
          Table = v783;
          v14 = v783;
          sqlite3VtabImportErrmsg(a1, v780);
          if ( SDWORD1(v853) > 0 )
          {
            v784 = (const char *)sqlite3_value_text(v779);
            sqlite3VdbeError(a1, "%s", v784);
            v14 = DWORD1(v853);
            Table = DWORD1(v853);
          }
          v9 = v822;
          sqlite3VdbeChangeEncoding(v779, v822);
          goto LABEL_50;
        }
        v766 = v765 - 1;
        if ( v766 )
        {
          v767 = v766 - 1;
          if ( v767 )
          {
            if ( v767 != 1 )
              goto LABEL_53;
            v768 = (_QWORD *)out2Prerelease(v4, v6);
            v769 = 32LL * *((int *)v6 + 1);
            v770 = *(_QWORD *)(v769 + *(_QWORD *)(v2 + 32) + 8);
            Page = 0;
            if ( *((_DWORD *)v6 + 3) )
            {
              Page = sqlite3BtreeLastPage(*(_QWORD *)(v769 + *(_QWORD *)(v2 + 32) + 8));
              if ( Page < *((_DWORD *)v6 + 3) )
                Page = *((_DWORD *)v6 + 3);
            }
            *v768 = (unsigned int)sqlite3BtreeMaxPageCount(v770, Page);
            goto LABEL_422;
          }
          v772 = (_QWORD *)out2Prerelease(v4, v6);
          *v772 = (unsigned int)sqlite3BtreeLastPage(*(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8));
LABEL_244:
          v3 = 0;
          goto LABEL_52;
        }
        v773 = *(_DWORD *)(v2 + 48);
        *(_QWORD *)(v2 + 48) |= 0x4000000uLL;
        v774 = *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL);
        v775 = v826 + 56LL * *((int *)v6 + 1);
        v776 = sqlite3VdbeChangeEncoding(v775, (unsigned int)v10);
        v3 = 0;
        v14 = v776;
        if ( v776 )
          goto LABEL_1546;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v774 + 152LL))(v774, *(_QWORD *)(v775 + 8));
        v14 = Table;
        if ( (v773 & 0x4000000) == 0 )
          *(_QWORD *)(v2 + 48) &= ~0x4000000uLL;
        sqlite3VtabImportErrmsg(v4, v774);
        *((_DWORD *)v4 + 50) &= 0xFFFFFFFC;
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        goto LABEL_79;
      }
      v789 = v15 - 181;
      if ( v789 )
      {
        v790 = v789 - 1;
        if ( !v790 )
        {
          v802 = 56LL * *((int *)v6 + 1);
          v803 = 56LL * *((int *)v6 + 2);
          if ( ((unsigned __int8)v10 & *(_BYTE *)(v802 + v7 + 20)) != 0 )
          {
            *(_WORD *)(v803 + v7 + 20) &= ~0x800u;
          }
          else
          {
            *(_WORD *)(v803 + v7 + 20) |= 0x800u;
            *(_BYTE *)(v803 + v7 + 23) = *(_BYTE *)(v802 + v7);
          }
          goto LABEL_196;
        }
        v791 = v790 - 1;
        if ( !v791 )
        {
          v799 = 56LL * *((int *)v6 + 1);
          v800 = filterHash(v7, v6);
          v801 = (v800 % (8 * *(_DWORD *)(v799 + v7 + 16))) >> 3;
          *(_BYTE *)(v801 + *(_QWORD *)(v799 + v7 + 8)) |= 1 << ((v800 % (8 * *(_DWORD *)(v799 + v7 + 16))) & 7);
          goto LABEL_244;
        }
        if ( v791 != 1 )
          goto LABEL_53;
        goto LABEL_1442;
      }
      v804 = 56LL * *((int *)v6 + 1);
      v674 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v804 + v7 + 20) & 0x800) != 0 )
      {
        sqlite3VdbeMemSetInt64(v674, *(unsigned __int8 *)(v804 + v7 + 23));
        goto LABEL_244;
      }
LABEL_1260:
      sqlite3VdbeMemSetNull(v674);
      goto LABEL_244;
    }
    if ( (_DWORD)v15 != 163 )
    {
      if ( (unsigned int)v15 <= 0x98 )
      {
        if ( (_DWORD)v15 == 152 )
        {
          sqlite3UnlinkAndDeleteIndex(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
          goto LABEL_244;
        }
        if ( (unsigned int)v15 <= 0x92 )
        {
          if ( (_DWORD)v15 == 146 )
          {
            v675 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( *(_BYTE *)v675 == (_BYTE)v10 )
            {
              sqlite3VdbeSorterReset(v2, *(_QWORD *)(v675 + 48));
              goto LABEL_244;
            }
            v71 = sqlite3BtreeClearTableOfCursor(*(_QWORD *)(v675 + 48));
            goto LABEL_153;
          }
          v654 = v15 - 141;
          if ( v654 )
          {
            v655 = v654 - 1;
            if ( v655 )
            {
              v656 = v655 - 1;
              if ( !v656 )
              {
                v667 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
                if ( !*(_BYTE *)(v667 + 3) )
                  goto LABEL_53;
                v71 = sqlite3VdbeFinishMoveto(v667);
                goto LABEL_153;
              }
              v657 = v656 - 1;
              if ( !v657 )
              {
                LODWORD(v831) = 0;
                v663 = out2Prerelease(v4, v6);
                *(_WORD *)(v663 + 20) = 1;
                if ( *(_DWORD *)(v2 + 220) > *(_DWORD *)(v2 + 232) + 1 )
                {
                  v14 = 6;
                  *((_BYTE *)v4 + 196) = 2;
                  goto LABEL_1523;
                }
                v664 = *((_DWORD *)v6 + 3);
                v665 = *(_QWORD *)(v2 + 32);
                v666 = *((unsigned int *)v6 + 1);
                LODWORD(v831) = 0;
                v14 = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v664 + v665 + 8), v666, &v831);
                Table = v14;
                v3 = 0;
                *(_WORD *)(v663 + 20) = 4;
                *(_QWORD *)v663 = (int)v831;
                if ( v14 )
                  goto LABEL_1546;
                if ( (_DWORD)v831 )
                {
                  sqlite3RootPageMoved(v2, v664, (unsigned int)v831, *((unsigned int *)v6 + 1));
                  v10 = 1;
                  v833 = v664 + 1;
LABEL_59:
                  v9 = v822;
LABEL_60:
                  v5 = v825;
LABEL_61:
                  v13 = v823;
                  v3 = 0;
                  goto LABEL_53;
                }
                v13 = v823;
                v10 = 1;
                goto LABEL_623;
              }
              if ( v657 != 1 )
                goto LABEL_53;
              v658 = *(_QWORD *)(v2 + 32);
              v659 = *((unsigned int *)v6 + 1);
              v660 = 32LL * *((int *)v6 + 2);
              v839 = 0;
              v661 = sqlite3BtreeClearTable(*(_QWORD *)(v660 + v658 + 8), v659, &v839);
              v3 = 0;
              Table = v661;
              v14 = v661;
              if ( *((_DWORD *)v6 + 3) )
              {
                v662 = v839;
                v4[7] += v839;
                if ( *((int *)v6 + 3) > 0 )
                  *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) += v662;
              }
              goto LABEL_1246;
            }
          }
          v668 = *((int *)v6 + 1);
          v669 = v4[15];
          v828 = 0;
          v670 = *(_QWORD *)(v669 + 8 * v668);
          v671 = sqlite3VdbeCursorRestore(v670);
          v3 = 0;
          Table = v671;
          v14 = v671;
          if ( v671 )
            goto LABEL_1546;
          if ( !*(_BYTE *)(v670 + 2) )
          {
            v828 = 0;
            v672 = sqlite3VdbeIdxRowid(v2, *(_QWORD *)(v670 + 48), &v828);
            v3 = 0;
            Table = v672;
            v14 = v672;
            if ( v672 )
              goto LABEL_1546;
            if ( *v6 == 0x8D )
            {
              v10 = v672 + 1;
              v673 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3));
              *(_BYTE *)(v673 + 2) = 0;
              *(_QWORD *)(v673 + 80) = v828;
              *(_BYTE *)(v673 + 3) = v672 + 1;
              *(_DWORD *)(v673 + 32) = 0;
              *(_QWORD *)(v673 + 16) = *((_QWORD *)v6 + 2);
              *(_QWORD *)(v673 + 40) = v670;
              goto LABEL_195;
            }
            v283 = (unsigned int **)out2Prerelease(v4, v6);
            v284 = v828;
            goto LABEL_536;
          }
          v674 = v7 + 56LL * *((int *)v6 + 2);
          goto LABEL_1260;
        }
        v676 = v15 - 147;
        if ( !v676 )
        {
          LODWORD(v829) = 0;
          v692 = out2Prerelease(v4, v6);
          v693 = *(_QWORD *)(v2 + 32);
          v694 = (_QWORD *)v692;
          v695 = *((unsigned int *)v6 + 3);
          v696 = 32LL * *((int *)v6 + 1);
          LODWORD(v829) = 0;
          v697 = sqlite3BtreeCreateTable(*(_QWORD *)(v696 + v693 + 8), &v829, v695);
          v3 = 0;
          Table = v697;
          v14 = v697;
          if ( v697 )
            goto LABEL_1546;
          *v694 = (unsigned int)v829;
          goto LABEL_52;
        }
        v677 = v676 - 1;
        if ( !v677 )
        {
          *(_BYTE *)(v2 + 112) += v10;
          v687 = *(_QWORD *)(v2 + 512);
          v688 = *(_BYTE *)(v2 + 110);
          v689 = *(_DWORD *)(v2 + 744);
          v828 = 0;
          if ( ((unsigned __int8)v10 & v6[4]) != 0 )
          {
            *(_QWORD *)(v2 + 512) = 0;
            *(_BYTE *)(v2 + 110) = 0;
          }
          if ( (v6[4] & 2) != 0 )
            *(_DWORD *)(v2 + 744) = *((_DWORD *)v6 + 2);
          v690 = sqlite3_exec(v2, *((_QWORD *)v6 + 2), 0, 0, (__int64)&v828);
          v691 = (const char *)v828;
          v3 = 0;
          --*(_BYTE *)(v2 + 112);
          v14 = v690;
          Table = v690;
          *(_QWORD *)(v2 + 512) = v687;
          *(_BYTE *)(v2 + 110) = v688;
          *(_DWORD *)(v2 + 744) = v689;
          if ( !v691 && !v690 )
            goto LABEL_79;
          sqlite3VdbeError(v4, "%s", v691);
          sqlite3_free(v828);
LABEL_1288:
          if ( v14 != 7 )
            goto LABEL_1523;
          goto LABEL_1543;
        }
        v678 = v677 - 1;
        if ( v678 )
        {
          v679 = v678 - 1;
          if ( v679 )
          {
            if ( v679 != 1 )
              goto LABEL_53;
            sqlite3UnlinkAndDeleteTable(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
            goto LABEL_244;
          }
          v71 = sqlite3AnalysisLoad(v2, *((unsigned int *)v6 + 1));
          goto LABEL_153;
        }
        v680 = *((int *)v6 + 1);
        v681 = *(_QWORD *)(v2 + 32);
        v835 = 0;
        *(_QWORD *)&v837 = 0;
        v836 = 0;
        if ( *((_QWORD *)v6 + 2) )
        {
          LODWORD(v836) = v680;
          *(_QWORD *)&v835 = v2;
          *((_QWORD *)&v835 + 1) = v4 + 21;
          DWORD2(v836) = 0;
          v683 = 32 * v680;
          v684 = sqlite3BtreeLastPage(*(_QWORD *)(v681 + v683 + 8));
          v685 = *(_QWORD *)(v2 + 32);
          LODWORD(v837) = v684;
          v686 = sqlite3MPrintf(
                   v2,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(v685 + v683),
                   "sqlite_master",
                   *((_QWORD *)v6 + 2));
          if ( !v686 )
          {
            v14 = 7;
LABEL_1533:
            sqlite3ResetAllSchemasOfConnection(v2);
            goto LABEL_1288;
          }
          *(_BYTE *)(v2 + 197) = 1;
          DWORD1(v836) = 0;
          HIDWORD(v836) = 0;
          v14 = sqlite3_exec(v2, v686, (unsigned int)sqlite3InitCallback, (unsigned int)&v835, 0);
          Table = v14;
          if ( !v14 )
          {
            v14 = DWORD1(v836);
            Table = DWORD1(v836);
            if ( !DWORD1(v836) && !HIDWORD(v836) )
            {
              v14 = sqlite3CorruptError(100436);
              Table = v14;
            }
          }
          sqlite3DbFreeNN(v2);
          v3 = 0;
          *(_BYTE *)(v2 + 197) = 0;
          v10 = 1;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v680 + v681 + 24));
          *(_DWORD *)(v2 + 44) &= ~0x10u;
          inited = sqlite3InitOne(v2, (unsigned int)v680, v4 + 21, *((unsigned __int16 *)v6 + 1));
          v10 = 1;
          Table = inited;
          *(_DWORD *)(v2 + 44) |= 1u;
          v14 = inited;
          *((_DWORD *)v4 + 50) &= 0xFFFFFFFC;
          v3 = 0;
        }
        if ( !v14 )
          goto LABEL_195;
        goto LABEL_1533;
      }
      if ( (unsigned int)v15 <= 0x9E )
      {
        if ( (_DWORD)v15 == 158 )
        {
          v717 = *((int *)v6 + 2);
          if ( (*(_DWORD *)(v2 + 48) & 0x80000) != 0 )
          {
            *(_QWORD *)(v2 + 768) += v717;
          }
          else if ( *((_DWORD *)v6 + 1) )
          {
            *(_QWORD *)(v2 + 760) += v717;
          }
          else
          {
            v4[10] += v717;
          }
          goto LABEL_53;
        }
        v698 = v15 - 153;
        if ( !v698 )
        {
          v282 = out2Prerelease(v4, v6);
          *(_WORD *)(v282 + 20) = 8;
          goto LABEL_534;
        }
        v699 = v698 - 1;
        if ( !v699 )
        {
          sqlite3UnlinkAndDeleteTrigger(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
          goto LABEL_244;
        }
        v700 = v699 - 1;
        if ( !v700 )
        {
          v705 = *((int *)v6 + 1);
          v706 = *((_QWORD *)v6 + 2);
          v707 = 56 * v705;
          v708 = v705 + 1;
          LODWORD(v829) = 0;
          v709 = *(_QWORD *)(v2 + 32);
          v710 = 56 * *((_DWORD *)v6 + 3);
          v828 = 0;
          v711 = v7 + 56LL * v708;
          Table = sqlite3BtreeIntegrityCheck(
                    v2,
                    *(_QWORD *)(32LL * *((unsigned __int16 *)v6 + 1) + v709 + 8),
                    (int)v706 + 4,
                    (int)v7 + v710,
                    *((_DWORD *)v6 + 2),
                    (int)v10 + *(_DWORD *)(v707 + v7),
                    (__int64)&v829,
                    (__int64)&v828);
          v14 = Table;
          sqlite3VdbeMemSetNull(v711);
          if ( (_DWORD)v829 )
          {
            if ( Table )
            {
              sqlite3_free(v828);
              goto LABEL_1523;
            }
            LOBYTE(v712) = 1;
            *(_QWORD *)(v707 + v7) -= (int)v829 - 1;
            sqlite3VdbeMemSetStr(v711, v828, -1, v712, sqlite3_free);
          }
          v9 = v822;
          sqlite3VdbeChangeEncoding(v711, v822);
          goto LABEL_1308;
        }
        v701 = v700 - 1;
        if ( !v701 )
        {
          v702 = *((int *)v6 + 1);
          v703 = *((int *)v6 + 2);
          v704 = v7 + 56 * v702;
          if ( (*(_BYTE *)(v704 + 20) & 0x10) != 0 || !(unsigned int)sqlite3VdbeMemSetRowSet(v7 + 56 * v702) )
          {
            sqlite3RowSetInsert(*(_QWORD *)(v704 + 8), *(_QWORD *)(56 * v703 + v7));
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        if ( v701 != 1 )
          goto LABEL_53;
        v322 = out2Prerelease(v4, v6);
        v321 = *(_QWORD *)(v4[33] + 24)
             + 56LL * (*((_DWORD *)v6 + 1) + *(_DWORD *)(*(_QWORD *)(v4[33] + 16) + 24LL * *(int *)(v4[33] + 76) + 4));
        goto LABEL_598;
      }
      v718 = v15 - 159;
      if ( !v718 )
      {
        v731 = v4[33];
        if ( v731 )
        {
          while ( *(_QWORD *)(v731 + 8) )
            v731 = *(_QWORD *)(v731 + 8);
          v732 = (_QWORD *)(*(_QWORD *)(v731 + 24) + 56LL * *((int *)v6 + 1));
        }
        else
        {
          v732 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 1));
        }
        sqlite3VdbeMemIntegerify(v732);
        v733 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 2));
        sqlite3VdbeMemIntegerify(v733);
        v3 = 0;
        v13 = v823;
        v10 = 1;
        if ( *v732 < *v733 )
          *v732 = *v733;
        goto LABEL_623;
      }
      v719 = v718 - 1;
      if ( !v719 )
      {
        v726 = *((int *)v6 + 3);
        v727 = 56LL * *((int *)v6 + 1);
        v828 = 0;
        v617 = out2Prerelease(v4, v6);
        v3 = 0;
        v828 = *(unsigned int **)(v727 + v826);
        if ( (__int64)v828 <= 0 )
        {
          v7 = v826;
        }
        else
        {
          v728 = 56 * v726;
          v7 = v826;
          v729 = *(_QWORD *)(v728 + v826);
          if ( v729 <= 0 )
            v729 = 0;
          v730 = sqlite3AddInt64(&v828, v729);
          v3 = 0;
          if ( !v730 )
          {
            v619 = (__int64)v828;
            goto LABEL_1195;
          }
        }
        *(_QWORD *)v617 = -1;
        goto LABEL_80;
      }
      if ( (unsigned int)(v719 - 1) > 1 )
        goto LABEL_53;
      v720 = *((unsigned __int16 *)v6 + 1);
      v721 = sqlite3DbMallocRawNN(v2, 8 * v720 + 104);
      if ( !v721 )
        goto LABEL_1543;
      *(_QWORD *)(v721 + 16) = 0;
      v722 = v721 + 8 * (v720 + 6);
      *(_QWORD *)v721 = v722;
      sqlite3VdbeMemInit(v722, v2, 1);
      v7 = v826;
      *(_QWORD *)(v721 + 8) = *((_QWORD *)v6 + 2);
      *(_BYTE *)(v721 + 42) = v720;
      *(_DWORD *)(v721 + 32) = -1431655765 * ((__int64)&v6[-v825] >> 3);
      v9 = v822;
      *(_QWORD *)(v721 + 24) = v4;
      *(_BYTE *)(v721 + 41) = 0;
      *(_DWORD *)(v721 + 36) = 0;
      LODWORD(v10) = 1;
      *(_BYTE *)(v721 + 40) = v822;
      *(_WORD *)v6 = -3677;
      *((_QWORD *)v6 + 2) = v721;
    }
    v723 = (_DWORD *)*((_QWORD *)v6 + 2);
    v724 = v7 + 56LL * *((int *)v6 + 3);
    if ( *((_QWORD *)v723 + 2) != v724 )
    {
      v725 = *((unsigned __int8 *)v723 + 42);
      *((_QWORD *)v723 + 2) = v724;
      while ( 1 )
      {
        v725 -= v10;
        if ( v725 < 0 )
          break;
        *(_QWORD *)&v723[2 * v725 + 12] = v7 + 56LL * (v725 + *((_DWORD *)v6 + 2));
      }
    }
    *(_DWORD *)(v724 + 16) += v10;
    v734 = v723 + 12;
    v735 = *((_QWORD *)v723 + 1);
    v736 = *((unsigned __int8 *)v723 + 42);
    if ( *((_DWORD *)v6 + 1) )
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v735 + 48))(v723, v736, v734);
    else
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v735 + 24))(v723, v736, v734);
    v737 = v723[9];
    v3 = 0;
    if ( !v737 )
      goto LABEL_1408;
    if ( v737 > 0 )
    {
      v738 = (const char *)sqlite3_value_text(*(_QWORD *)v723);
      sqlite3VdbeError(v4, "%s", v738);
      v14 = v723[9];
      Table = v14;
    }
    if ( *((_BYTE *)v723 + 41) )
    {
      if ( *((_DWORD *)v6 - 5) )
        sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 - 5), 1);
      *((_BYTE *)v723 + 41) = 0;
    }
    sqlite3VdbeMemRelease(*(_QWORD *)v723);
    v3 = 0;
    v10 = 1;
    *(_WORD *)(*(_QWORD *)v723 + 20LL) = 1;
    v723[9] = 0;
    if ( v14 )
      goto LABEL_1546;
    goto LABEL_195;
  }
  if ( (_DWORD)v15 == 92 )
  {
    if ( ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 1) + v7 + 20)) != 0
      || ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 3) + v7 + 20)) != 0 )
    {
      v340 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v340 + 20) & 0x9000) == 0 )
      {
        *(_WORD *)(v340 + 20) = v10;
        goto LABEL_53;
      }
      v137 = v7 + 56LL * *((int *)v6 + 2);
      goto LABEL_248;
    }
    v318 = *((int *)v6 + 2);
    goto LABEL_589;
  }
  if ( (unsigned int)v15 <= 0x2D )
  {
    if ( (_DWORD)v15 != 45 )
    {
      if ( (unsigned int)v15 <= 0x16 )
      {
        if ( (_DWORD)v15 == 22 )
          goto LABEL_225;
        if ( (unsigned int)v15 <= 0xB )
        {
          if ( (_DWORD)v15 == 11 )
          {
            v99 = 56LL * *((int *)v6 + 1);
            *(_QWORD *)(v99 + v7) = *((_DWORD *)v6 + 3) - (int)v10;
            *(_WORD *)(v99 + v7 + 20) = 4;
            if ( !*((_DWORD *)v6 + 2) )
              goto LABEL_53;
          }
          else
          {
            if ( (unsigned int)v15 <= 5 )
            {
              if ( (_DWORD)v15 != 5 )
              {
                if ( (_DWORD)v15 )
                {
                  v17 = v15 - 1;
                  if ( v17 )
                  {
                    v18 = v17 - 1;
                    if ( v18 )
                    {
                      v19 = v18 - 1;
                      if ( v19 )
                      {
                        if ( v19 != 1 )
                          goto LABEL_53;
                        v20 = out2Prerelease(v4, v6);
                        v21 = *((_DWORD *)v6 + 3);
                        v22 = *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8);
                        v23 = sqlite3BtreePager(v22);
                        JournalMode = sqlite3PagerGetJournalMode(v23);
                        v25 = JournalMode;
                        if ( v21 == -1 )
                          v21 = JournalMode;
                        if ( !(unsigned int)sqlite3PagerOkToChangeJournalMode(v23) )
                          v21 = v25;
                        v26 = sqlite3PagerFilename(v23, 1);
                        if ( v21 == 5
                          && (!(unsigned int)sqlite3Strlen30(v26) || !(unsigned int)sqlite3PagerWalSupported(v23)) )
                        {
                          v21 = v25;
LABEL_32:
                          v14 = Table;
                          goto LABEL_33;
                        }
                        if ( v21 == v25 || v25 != 5 && v21 != 5 )
                          goto LABEL_32;
                        if ( *(_BYTE *)(v2 + 101) && *(int *)(v2 + 220) <= 1 )
                        {
                          if ( v25 == 5 )
                          {
                            Table = sqlite3PagerCloseWal(v23, v2);
                            if ( !Table )
                            {
                              sqlite3PagerSetJournalMode(v23, v21);
LABEL_46:
                              v14 = sqlite3BtreeSetVersion(v22, (unsigned int)(v21 == 5) + 1);
                              Table = v14;
LABEL_33:
                              if ( !v14 )
                              {
LABEL_49:
                                v27 = sqlite3PagerSetJournalMode(v23, v21);
                                *(_WORD *)(v20 + 20) = 8706;
                                v28 = sqlite3JournalModename(v27);
                                *(_QWORD *)(v20 + 8) = v28;
                                v9 = v822;
                                *(_DWORD *)(v20 + 16) = sqlite3Strlen30(v28);
                                *(_BYTE *)(v20 + 22) = 1;
                                sqlite3VdbeChangeEncoding(v20, v822);
                                v4 = a1;
LABEL_50:
                                v3 = 0;
                                if ( v14 )
                                  goto LABEL_1546;
LABEL_51:
                                v7 = v826;
                                goto LABEL_52;
                              }
LABEL_48:
                              v21 = v25;
                              goto LABEL_49;
                            }
                          }
                          else
                          {
                            if ( v25 == 4 )
                              sqlite3PagerSetJournalMode(v23, 2);
                            if ( !Table )
                              goto LABEL_46;
                          }
                          v14 = Table;
                          goto LABEL_48;
                        }
                        v4 = a1;
                        v805 = "into";
                        v14 = 1;
                        v806 = "cannot change %s wal mode from within a transaction";
                        if ( v21 != 5 )
                          v805 = "out of";
LABEL_1538:
                        sqlite3VdbeError(v4, v806, v805);
                        goto LABEL_1523;
                      }
                      v29 = *((_DWORD *)v6 + 2);
                      v30 = *((_DWORD *)v6 + 1);
                      v859 = 0;
                      v860 = -1;
                      v31 = sqlite3Checkpoint(v2, v30, v29, (unsigned int)&v860, (__int64)&v860 + 4);
                      v3 = 0;
                      Table = v31;
                      v14 = v31;
                      if ( v31 )
                      {
                        if ( v31 != 5 )
                          goto LABEL_1546;
                        v14 = 0;
                        Table = 0;
                        v859 = 1;
                      }
                      v32 = 0;
                      v33 = v7 + 56LL * *((int *)v6 + 3);
                      do
                      {
                        sqlite3VdbeMemSetInt64(v33, *(&v859 + v32));
                        v10 = 1;
                        v33 += 56;
                        ++v32;
                      }
                      while ( v32 != 3 );
                      goto LABEL_59;
                    }
                    v34 = *((unsigned int *)v6 + 2);
                    LODWORD(v829) = 0;
                    if ( (_DWORD)v34 && (*(_QWORD *)(v2 + 48) & 0x200100000LL) != 0 )
                    {
                      v14 = (*(_QWORD *)(v2 + 48) & 0x100000LL) != 0 ? 8 : 11;
                      goto LABEL_1546;
                    }
                    v35 = *(_QWORD *)(v2 + 32);
                    v36 = 32LL * *((int *)v6 + 1);
                    v37 = *(_QWORD *)(v36 + v35 + 8);
                    if ( v37 )
                    {
                      v38 = sqlite3BtreeBeginTrans(*(_QWORD *)(v36 + v35 + 8), v34, &v829);
                      v3 = 0;
                      Table = v38;
                      v14 = v38;
                      if ( v38 )
                      {
                        if ( (_BYTE)v38 == 5 )
                        {
                          *((_DWORD *)v4 + 13) = v38;
                          *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v825] >> 3);
                          goto LABEL_1564;
                        }
                        goto LABEL_1546;
                      }
                      if ( (v4[25] & 0x20) == 0
                        || !*((_DWORD *)v6 + 2)
                        || *(_BYTE *)(v2 + 101) && *(int *)(v2 + 220) <= 1 )
                      {
LABEL_76:
                        if ( *((_WORD *)v6 + 1)
                          && ((_DWORD)v829 != *((_DWORD *)v6 + 3)
                           || *(_DWORD *)(*(_QWORD *)(v36 + v35 + 24) + 4LL) != *((_DWORD *)v6 + 4)) )
                        {
                          if ( v4[21] )
                            sqlite3DbFreeNN(v2);
                          v4[21] = sqlite3DbStrDup(v2, "database schema has changed");
                          if ( **(_DWORD **)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 24) != (_DWORD)v829 )
                            sqlite3ResetOneSchema(v2);
                          v14 = 17;
                          *((_DWORD *)v4 + 50) = v4[25] & 0xFFFFFFEC | 1;
                          goto LABEL_1523;
                        }
                        goto LABEL_79;
                      }
                      v39 = *((_DWORD *)v4 + 16);
                      if ( !v39 )
                      {
                        v39 = ++*(_DWORD *)(v2 + 756) + *(_DWORD *)(v2 + 752);
                        *((_DWORD *)v4 + 16) = v39;
                      }
                      v40 = sqlite3VtabSavepoint(v2, 0, (unsigned int)(v39 - 1));
                      v3 = 0;
                      Table = v40;
                      v14 = v40;
                      if ( !v40 )
                      {
                        v14 = sqlite3BtreeBeginStmt(v37, *((unsigned int *)v4 + 16));
                        Table = v14;
                        v3 = 0;
                      }
                      v4[11] = *(_QWORD *)(v2 + 760);
                      v4[12] = *(_QWORD *)(v2 + 768);
                    }
                    if ( v14 )
                      goto LABEL_1546;
                    goto LABEL_76;
                  }
                  v807 = *((_DWORD *)v6 + 1);
                  v808 = *((_DWORD *)v6 + 2);
                  if ( v807 != *(unsigned __int8 *)(v2 + 101) )
                  {
                    if ( v808 )
                    {
                      sqlite3RollbackAll(v2, 516);
                      v809 = 1;
                    }
                    else
                    {
                      if ( v807 && *(int *)(v2 + 224) > 0 )
                      {
                        sqlite3VdbeError(v4, "cannot commit transaction - SQL statements in progress");
                        goto LABEL_1485;
                      }
                      v14 = sqlite3VdbeCheckFk(v4, (unsigned int)v10);
                      if ( v14 )
                        goto LABEL_1564;
                      v809 = v807;
                    }
                    *(_BYTE *)(v2 + 101) = v809;
                    if ( (unsigned int)sqlite3VdbeHalt(v4) == 5 )
                    {
                      v14 = 5;
                      *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v825] >> 3);
                      *(_BYTE *)(v2 + 101) = 1 - v807;
                      *((_DWORD *)v4 + 13) = 5;
                    }
                    else
                    {
                      sqlite3CloseSavepoints(v2);
                      v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
                    }
                    goto LABEL_1564;
                  }
                  if ( v807 )
                  {
                    v810 = "cannot rollback - no transaction is active";
                    if ( !v808 )
                      v810 = "cannot commit - no transaction is active";
                    sqlite3VdbeError(v4, v810);
                  }
                  else
                  {
                    sqlite3VdbeError(v4, "cannot start a transaction within a transaction");
                  }
                }
                else
                {
                  v41 = *((_DWORD *)v6 + 1);
                  v42 = (_BYTE *)*((_QWORD *)v6 + 2);
                  v834 = v41;
                  if ( !v41 )
                  {
                    if ( *(int *)(v2 + 224) <= 0 )
                    {
                      if ( v42 )
                      {
                        v44 = -1;
                        do
                          ++v44;
                        while ( v42[v44] );
                        v43 = v44 & 0x3FFFFFFF;
                      }
                      else
                      {
                        v43 = 0;
                      }
                      v45 = sqlite3VtabSavepoint(v2, 0, (unsigned int)(*(_DWORD *)(v2 + 752) + *(_DWORD *)(v2 + 756)));
                      v3 = 0;
                      Table = v45;
                      v14 = v45;
                      if ( !v45 )
                      {
                        v46 = (_QWORD *)sqlite3DbMallocRawNN(v2, v43 + 33LL);
                        v3 = 0;
                        v47 = v46;
                        if ( v46 )
                        {
                          *v46 = v46 + 4;
                          memcpy_0(v46 + 4, v42, v43 + 1);
                          v3 = 0;
                          if ( *(_BYTE *)(v2 + 101) )
                          {
                            *(_BYTE *)(v2 + 101) = 0;
                            *(_BYTE *)(v2 + 109) = 1;
                          }
                          else
                          {
                            ++*(_DWORD *)(v2 + 752);
                          }
                          v47[3] = *(_QWORD *)(v2 + 736);
                          v48 = *(_QWORD *)(v2 + 760);
                          *(_QWORD *)(v2 + 736) = v47;
                          v47[1] = v48;
                          v47[2] = *(_QWORD *)(v2 + 768);
                        }
                        goto LABEL_143;
                      }
                      goto LABEL_1546;
                    }
                    sqlite3VdbeError(v4, "cannot open savepoint - SQL statements in progress");
                    goto LABEL_1485;
                  }
                  v49 = *(_QWORD **)(v2 + 736);
                  for ( m = 0; ; ++m )
                  {
                    LODWORD(v831) = m;
                    if ( !v49 )
                      break;
                    v51 = sqlite3StrICmp(*v49, v42);
                    v3 = 0;
                    if ( !v51 )
                    {
                      v10 = 1;
                      if ( *(int *)(v2 + 224) <= 0 || v41 != 1 )
                      {
                        v52 = (unsigned int *)(v49 + 3);
                        v828 = (unsigned int *)(v49 + 3);
                        if ( v49[3] || !*(_BYTE *)(v2 + 109) )
                        {
                          LODWORD(v829) = 0;
                        }
                        else
                        {
                          LODWORD(v829) = 1;
                          v53 = 1;
                          if ( v41 == 1 )
                          {
                            v54 = sqlite3VdbeCheckFk(a1, 1);
                            if ( !v54 )
                            {
                              *(_BYTE *)(v830 + 101) = 1;
                              v55 = sqlite3VdbeHalt(a1);
                              v56 = v830;
                              if ( v55 == 5 )
                              {
                                v4 = a1;
                                v14 = 5;
                                *((_DWORD *)a1 + 12) = -1431655765 * ((__int64)&v6[-v825] >> 3);
                                *(_BYTE *)(v56 + 101) = 0;
                                *((_DWORD *)a1 + 13) = 5;
                                goto LABEL_1565;
                              }
                              v57 = *((_DWORD *)a1 + 13);
                              v3 = 0;
                              Table = v57;
                              if ( v57 )
                                *(_BYTE *)(v830 + 101) = 0;
                              else
                                *(_BYTE *)(v830 + 109) = 0;
                              v58 = (int *)(v56 + 752);
                              v10 = 1;
                              goto LABEL_129;
                            }
                            v14 = v54;
                            v4 = a1;
LABEL_1564:
                            v56 = v830;
                            goto LABEL_1565;
                          }
                        }
                        v58 = (int *)(v2 + 752);
                        v59 = *v58;
                        if ( v41 == 2 )
                        {
                          v60 = v830;
                          v61 = 0;
                          v62 = *(_DWORD *)(v830 + 44) & 1;
                          if ( *(int *)(v830 + 40) > 0 )
                          {
                            do
                            {
                              v63 = sqlite3BtreeTripAllCursors(
                                      *(_QWORD *)(32LL * v61 + *(_QWORD *)(v60 + 32) + 8),
                                      516,
                                      v62 ^ 1u);
                              v3 = 0;
                              Table = v63;
                              if ( v63 )
                                goto LABEL_1544;
                              v60 = v830;
                              v10 = 1;
                              ++v61;
                            }
                            while ( v61 < *(_DWORD *)(v830 + 40) );
                            m = (unsigned int)v831;
                          }
                        }
                        else
                        {
                          v62 = 0;
                        }
                        v56 = v830;
                        m = v59 + ~m;
                        v64 = 0;
                        if ( *(int *)(v830 + 40) > 0 )
                        {
                          v65 = v834;
                          while ( 1 )
                          {
                            v57 = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v64 + *(_QWORD *)(v56 + 32) + 8), v65, m);
                            v3 = 0;
                            Table = v57;
                            if ( v57 )
                              goto LABEL_1544;
                            v56 = v830;
                            v10 = 1;
                            if ( ++v64 >= *(_DWORD *)(v830 + 40) )
                              goto LABEL_123;
                          }
                        }
                        v57 = Table;
LABEL_123:
                        if ( v62 )
                        {
                          for ( n = *(_QWORD *)(v56 + 8); n; n = *(_QWORD *)(n + 16) )
                          {
                            *(_DWORD *)(n + 200) &= ~2u;
                            *(_DWORD *)(n + 200) |= 1u;
                          }
                          sqlite3ResetAllSchemasOfConnection(v56);
                          v56 = v830;
                          v10 = 1;
                          v57 = Table;
                          *(_DWORD *)(v830 + 44) |= 1u;
                          v3 = 0;
                        }
                        v52 = v828;
                        v53 = v829;
                        v41 = v834;
LABEL_129:
                        if ( v57 )
                        {
LABEL_1544:
                          v14 = Table;
                        }
                        else
                        {
                          v67 = *(_QWORD **)(v56 + 736);
                          if ( v67 != v49 )
                          {
                            do
                            {
                              *(_QWORD *)(v56 + 736) = v67[3];
                              sqlite3DbFreeNN(v56);
                              v56 = v830;
                              v10 = 1;
                              --*v58;
                              v67 = *(_QWORD **)(v56 + 736);
                            }
                            while ( v67 != v49 );
                            v3 = 0;
                          }
                          if ( v41 == 1 )
                          {
                            *(_QWORD *)(v56 + 736) = *(_QWORD *)v52;
                            sqlite3DbFreeNN(v56);
                            v3 = 0;
                            if ( !v53 )
                            {
                              --*v58;
                              v68 = v830;
                              goto LABEL_138;
                            }
                            v14 = Table;
LABEL_142:
                            v4 = a1;
LABEL_143:
                            v10 = 1;
LABEL_144:
                            if ( *((_BYTE *)v4 + 199) == 3 )
                            {
                              v14 = 101;
                              goto LABEL_1564;
                            }
LABEL_145:
                            v7 = v826;
LABEL_146:
                            v5 = v825;
LABEL_147:
                            v13 = v823;
LABEL_148:
                            v9 = v822;
LABEL_53:
                            v2 = v830;
                            v6 += 24;
                            v8 = v843;
                            goto LABEL_9;
                          }
                          v68 = v830;
                          *(_QWORD *)(v830 + 760) = v49[1];
                          *(_QWORD *)(v68 + 768) = v49[2];
                          if ( v53 && v41 != 2 )
                          {
                            v14 = Table;
                            v4 = a1;
                            goto LABEL_144;
                          }
LABEL_138:
                          v69 = sqlite3VtabSavepoint(v68, v41, m);
                          v3 = 0;
                          Table = v69;
                          v14 = v69;
                          if ( !v69 )
                            goto LABEL_142;
                        }
LABEL_1545:
                        v4 = a1;
LABEL_1546:
                        v814 = v830;
                        if ( *(_BYTE *)(v830 + 103) == (_BYTE)v3 )
                        {
                          if ( v14 == 8458 )
                          {
                            v14 = sqlite3CorruptError(102468);
                            v3 = 0;
                          }
                        }
                        else
                        {
                          v14 = 7;
                        }
                        if ( v4[21] == v3 && v14 != 3082 )
                        {
                          v815 = (const char *)sqlite3ErrStr(v14);
                          sqlite3VdbeError(v4, "%s", v815);
                        }
                        *((_DWORD *)v4 + 13) = v14;
                        sqlite3SystemError(v814, v14);
                        sqlite3_log(
                          v14,
                          "statement aborts at %d: [%s] %s",
                          -1431655765 * ((__int64)&v6[-v825] >> 3),
                          (const char *)v4[31],
                          (const char *)v4[21]);
                        if ( *((_BYTE *)v4 + 199) == 2 )
                          sqlite3VdbeHalt(v4);
                        if ( v14 == 3082 )
                        {
                          sqlite3OomFault(v814);
                          goto LABEL_1557;
                        }
                        if ( v14 == 11 )
                        {
                          v56 = v814;
                          if ( !*(_BYTE *)(v814 + 101) )
                            *(_QWORD *)(v814 + 48) |= 0x200000000uLL;
                        }
                        else
                        {
LABEL_1557:
                          v56 = v814;
                        }
                        v14 = 1;
                        if ( v833 )
                        {
                          sqlite3ResetOneSchema(v56);
                          v56 = v814;
                        }
                        goto LABEL_1565;
                      }
                      v4 = a1;
                      sqlite3VdbeError(a1, "cannot release savepoint - SQL statements in progress");
LABEL_1485:
                      v14 = 5;
LABEL_1523:
                      v3 = 0;
                      goto LABEL_1546;
                    }
                    v49 = (_QWORD *)v49[3];
                  }
                  v4 = a1;
                  sqlite3VdbeError(a1, "no such savepoint: %s", v42);
                }
                v14 = 1;
                goto LABEL_1523;
              }
              if ( *((_DWORD *)v6 + 2) )
                v70 = v7 + 56LL * *((int *)v6 + 2);
              else
                v70 = 0;
              v71 = sqlite3RunVacuum(v4 + 21, v2, *((unsigned int *)v6 + 1), v70);
              goto LABEL_153;
            }
            v73 = v15 - 6;
            if ( v73 )
            {
              v74 = v73 - 1;
              if ( v74 )
              {
                v75 = v74 - 1;
                if ( v75 )
                {
                  v76 = v75 - 1;
                  if ( v76 )
                  {
                    if ( v76 != 1 )
                      goto LABEL_53;
                    v77 = 56LL * *((int *)v6 + 1);
                    *(_WORD *)(v77 + v7 + 20) = 4;
                    *(_QWORD *)(v77 + v7) = (int)(-1431655765 * ((__int64)&v6[-v5] >> 3));
                  }
                  goto LABEL_504;
                }
LABEL_1442:
                v792 = *(_BYTE *)(v2 + 110);
                if ( (v792 & 0x41) != 0 && *((_BYTE *)v4 + 197) != 0xFE )
                {
                  v793 = (const char *)*((_QWORD *)v6 + 2);
                  if ( v793 || (v793 = (const char *)v4[31]) != 0 )
                  {
                    if ( (v792 & 0x40) != 0 )
                    {
                      v794 = sqlite3VdbeExpandSql(v4, v793);
                      (*(void (__fastcall **)(_QWORD, __int64))(v2 + 248))(*(_QWORD *)(v2 + 256), v794);
                      sqlite3_free(v794);
                    }
                    else if ( *(_DWORD *)(v2 + 228) <= (int)v10 )
                    {
                      (*(void (__fastcall **)(_QWORD, _QWORD, __int64 *))(v2 + 248))(
                        (unsigned int)v10,
                        *(_QWORD *)(v2 + 256),
                        v4);
                    }
                    else
                    {
                      v795 = sqlite3MPrintf(v2, "-- %s", v793);
                      (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v2 + 248))(
                        1,
                        *(_QWORD *)(v2 + 256),
                        v4,
                        v795);
                      sqlite3DbFree(v2, v795);
                    }
                    v5 = v825;
                    v3 = 0;
                    v13 = v823;
                    v10 = 1;
                  }
                }
                v796 = *((_DWORD *)v6 + 1);
                if ( v796 >= dword_18010EFF8 )
                {
                  if ( *v6 == 0xB8 )
                    goto LABEL_53;
                  for ( ii = v10; ii < *((_DWORD *)v4 + 36); ii += v10 )
                  {
                    v798 = v4[17];
                    if ( *(_BYTE *)(v798 + 24LL * ii) == 15 )
                      *(_DWORD *)(v798 + 24LL * ii + 4) = 0;
                  }
                  v796 = 0;
                }
                *((_DWORD *)v6 + 1) = v796 + 1;
                *((_DWORD *)v4 + 59) += v10;
                goto LABEL_215;
              }
              v828 = 0;
              if ( !*(_BYTE *)(v2 + 103) )
              {
                v78 = *(__int64 **)(*((_QWORD *)v6 + 2) + 16LL);
                if ( v78 )
                {
                  v3 = *v78;
                  if ( *v78 )
                  {
                    if ( !*(_QWORD *)(v3 + 104) )
                    {
                      v3 = 0;
                      goto LABEL_952;
                    }
                    v79 = 0;
                    v80 = *((unsigned int *)v6 + 2);
                    v81 = *(_BYTE *)(v2 + 108);
                    v82 = v4[14];
                    v83 = v7 + 56LL * *((int *)v6 + 3);
                    if ( (int)v80 > 0 )
                    {
                      do
                      {
                        v84 = (unsigned int)v79++;
                        *(_QWORD *)(v82 + 8 * v84) = v83;
                        v83 += 56;
                      }
                      while ( v79 < (int)v80 );
                      v7 = v826;
                    }
                    *(_BYTE *)(v2 + 108) = v6[2];
                    Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int **))(v3 + 104))(
                              v78,
                              v80,
                              v82,
                              &v828);
                    *(_BYTE *)(v2 + 108) = v81;
                    v14 = Table;
                    sqlite3VtabImportErrmsg(v4, v78);
                    v3 = 0;
                    if ( !Table )
                    {
                      if ( *((_DWORD *)v6 + 1) )
                        *(_QWORD *)(v2 + 56) = v828;
                      goto LABEL_172;
                    }
                    if ( (_BYTE)Table != 19 || !*(_BYTE *)(*((_QWORD *)v6 + 2) + 28LL) )
                    {
LABEL_172:
                      v10 = 1;
                      ++v4[7];
                      goto LABEL_173;
                    }
                    v85 = *((_WORD *)v6 + 1);
                    if ( v85 != 4 )
                    {
                      if ( v85 == 5 )
                        LOBYTE(v85) = 2;
                      *((_BYTE *)v4 + 196) = v85;
                      goto LABEL_1546;
                    }
                    v14 = 0;
                    Table = 0;
                    goto LABEL_950;
                  }
                }
LABEL_1504:
                v14 = 6;
                goto LABEL_1546;
              }
LABEL_1543:
              sqlite3OomFault(v2);
              sqlite3VdbeError(v4, "out of memory");
              v14 = 7;
              goto LABEL_1523;
            }
            v86 = 56LL * *((int *)v6 + 3);
            v87 = a1[14];
            v88 = (int *)(v86 + v7 + 56);
            v89 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v90 = *v88;
            v91 = *(__int64 ***)(v89 + 48);
            v92 = *(unsigned int *)(v86 + v826);
            v93 = *v91;
            v94 = **v91;
            if ( *v88 > 0 )
            {
              do
              {
                v95 = (unsigned int)v3;
                LODWORD(v3) = v3 + 1;
                *(_QWORD *)(v87 + 8 * v95) = &v88[14 * (int)v3];
              }
              while ( (int)v3 < v90 );
            }
            HIDWORD(v821) = HIDWORD(v87);
            v96 = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v94 + 64))(v91, v92, *((_QWORD *)v6 + 2));
            v97 = v93;
            Table = v96;
            v4 = a1;
            v14 = v96;
            sqlite3VtabImportErrmsg(a1, v97);
            v3 = 0;
            if ( v14 )
              goto LABEL_1546;
            v98 = (*(__int64 (__fastcall **)(__int64 **))(v94 + 80))(v91);
            v3 = 0;
            v10 = 1;
            *(_BYTE *)(v89 + 2) = 0;
            if ( !v98 )
              goto LABEL_145;
          }
          goto LABEL_1219;
        }
        if ( (unsigned int)v15 <= 0x11 )
        {
          if ( (_DWORD)v15 == 17 )
          {
            v119 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((_DWORD *)v6 + 3) == 0);
            v3 = 0;
            v10 = 1;
            if ( v119 )
              goto LABEL_195;
            goto LABEL_1219;
          }
          v100 = v15 - 12;
          if ( v100 )
          {
            v101 = v100 - 1;
            if ( v101 )
            {
              v102 = v101 - 1;
              if ( v102 )
              {
                v103 = v102 - 1;
                if ( v103 )
                {
                  if ( v103 != 1 )
                    goto LABEL_53;
                  v104 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((unsigned int *)v6 + 3));
                  v3 = 0;
                  v105 = v104 == 0;
                  goto LABEL_194;
                }
                v106 = v4[33];
                if ( v106 )
                {
                  v107 = *(_QWORD *)(v106 + 40);
                  v108 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v6[-v4[17]] >> 3)) >> 3;
                  v109 = (-85 * (unsigned __int8)((__int64)&v6[-v4[17]] >> 3)) & 7;
                  v110 = *(unsigned __int8 *)(v108 + v107);
                  if ( !_bittest(&v110, v109) )
                  {
                    v111 = v110 | (1 << v109);
                    v13 = v823;
                    *(_BYTE *)(v108 + v107) = v111;
LABEL_201:
                    *((_DWORD *)v6 + 1) = *(_DWORD *)(v4[17] + 4);
LABEL_202:
                    v5 = v825;
                    goto LABEL_53;
                  }
                }
                else if ( *(_DWORD *)(v4[17] + 4) != *((_DWORD *)v6 + 1) )
                {
                  goto LABEL_201;
                }
LABEL_214:
                v5 = v825;
LABEL_215:
                v4 = a1;
                v7 = v826;
                v6 = (unsigned __int8 *)(v5 + 24LL * (*((_DWORD *)v6 + 2) - (int)v10));
                goto LABEL_196;
              }
              if ( (int)v13 >= 0 )
              {
                if ( (_DWORD)v13 )
                  v112 = *((_DWORD *)v6 + 3);
                else
                  v112 = *((_DWORD *)v6 + 2);
              }
              else
              {
                v112 = *((_DWORD *)v6 + 1);
              }
              v113 = v112 - (int)v10;
LABEL_206:
              v6 = (unsigned __int8 *)(v5 + 24 * v113);
              goto LABEL_53;
            }
            v114 = v7 + 56LL * *((int *)v6 + 1);
            v115 = *(_WORD *)(v114 + 20);
            if ( (v115 & 4) == 0 )
            {
              LOBYTE(v5) = v9;
              LOBYTE(v13) = 67;
              applyAffinity(v7 + 56LL * *((int *)v6 + 1), v13, v5);
              v115 = *(_WORD *)(v114 + 20);
              v3 = 0;
              if ( (v115 & 4) == 0 )
              {
                if ( !*((_DWORD *)v6 + 2) )
                {
                  v14 = 20;
                  goto LABEL_1546;
                }
LABEL_213:
                v10 = 1;
                goto LABEL_214;
              }
              v5 = v825;
              v10 = 1;
              v13 = v823;
            }
            *(_WORD *)(v114 + 20) = v115 & 0xF240 | 4;
            goto LABEL_53;
          }
          v116 = 56LL * *((int *)v6 + 1);
          *(_WORD *)(v116 + v7 + 20) = 4;
          v117 = *(int *)(v116 + v7);
          *(_QWORD *)(v116 + v7) = (int)(-1431655765 * ((__int64)&v6[-v5] >> 3));
          v118 = 3 * v117;
LABEL_219:
          v6 = (unsigned __int8 *)(v5 + 8 * v118);
          goto LABEL_196;
        }
        if ( (_DWORD)v15 != 18 )
        {
          if ( (_DWORD)v15 != 19 )
          {
            if ( (_DWORD)v15 == 20 )
            {
              v131 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
              if ( !v131 || !*(_BYTE *)(v131 + 2) )
                goto LABEL_196;
              v132 = v7 + 56LL * *((int *)v6 + 3);
              if ( (*(_WORD *)(v132 + 20) & 0x9000) == 0 )
              {
                *(_WORD *)(v132 + 20) = v10;
                goto LABEL_215;
              }
              vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 3));
              v3 = 0;
              goto LABEL_213;
            }
LABEL_225:
            v120 = *((int *)v6 + 1);
            *(_QWORD *)&v837 = 0;
            v121 = v4[15];
            v122 = 0;
            LODWORD(v831) = 0;
            v835 = 0;
            v836 = 0;
            v123 = *(_QWORD *)(v121 + 8 * v120);
            *(_WORD *)(v123 + 2) = 0;
            *(_DWORD *)(v123 + 32) = 0;
            if ( *(_BYTE *)(v123 + 4) )
            {
              v124 = v826 + 56LL * *((int *)v6 + 3);
              v125 = *(_WORD *)(v124 + 20);
              if ( (v125 & 0x2E) == 2 )
                applyNumericAffinity(v124, 0);
              v126 = sqlite3VdbeIntValue(v124);
              v127 = *(_WORD *)(v124 + 20);
              v128 = v126;
              *(_WORD *)(v124 + 20) = v125;
              if ( (v127 & 0x24) == 0 )
              {
                if ( (v127 & 8) == 0 )
                {
                  v3 = 0;
                  if ( (v127 & 1) != 0 || (unsigned int)v15 >= 0x17 )
                  {
                    v14 = Table;
                    goto LABEL_1218;
                  }
                  v129 = *(_BYTE **)(v123 + 48);
                  if ( !*v129 && (v129[1] & 8) != 0 )
                  {
                    v130 = 0;
                    Table = 0;
                    v14 = 0;
                    goto LABEL_278;
                  }
                  v149 = btreeLast(v129, &v831);
                  v3 = 0;
                  Table = v149;
                  v14 = v149;
                  if ( v149 )
                    goto LABEL_1545;
                  goto LABEL_277;
                }
                v150 = sqlite3IntFloatCompare(v126);
                if ( v150 <= 0 )
                {
                  if ( v150 < 0 && (v15 & 1) != 0 )
                    LODWORD(v15) = v15 + 1;
                }
                else if ( (v15 & 1) == 0 )
                {
                  LODWORD(v15) = v15 - 1;
                }
              }
              v151 = (_QWORD *)(v123 + 48);
              v152 = sqlite3BtreeTableMoveto(*(_QWORD *)(v123 + 48), v128, 0, &v831);
              v3 = 0;
              *(_QWORD *)(v123 + 80) = v128;
              Table = v152;
              v14 = v152;
              if ( v152 )
                goto LABEL_1545;
            }
            else
            {
              v151 = (_QWORD *)(v123 + 48);
              v153 = *(_BYTE *)(*(_QWORD *)(v123 + 48) + 3LL) & 2;
              *(_QWORD *)&v835 = *(_QWORD *)(v123 + 56);
              LOBYTE(v122) = v153 != 0;
              WORD6(v836) = *((_WORD *)v6 + 8);
              BYTE2(v837) = 0;
              v154 = *((int *)v6 + 3);
              BYTE14(v836) = v10 + (((unsigned __int8)v10 & (unsigned __int8)(v15 - 1)) != 0 ? 0xFE : 0);
              *((_QWORD *)&v835 + 1) = v826 + 56 * v154;
              v155 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v123 + 48), &v835, &v831);
              v3 = 0;
              Table = v155;
              v14 = v155;
              if ( v155 )
                goto LABEL_1545;
              if ( v153 )
              {
                if ( !BYTE2(v837) )
                  goto LABEL_277;
              }
              else
              {
                v122 = 0;
              }
            }
            if ( (int)v15 < 23 )
            {
              if ( (int)v831 <= 0 && ((_DWORD)v831 || (_DWORD)v15 != 21) )
              {
                v130 = *(_BYTE *)*v151 != 0;
                goto LABEL_278;
              }
              LODWORD(v831) = 0;
              v156 = sqlite3BtreePrevious(*v151, 0);
            }
            else
            {
              if ( (int)v831 >= 0 && ((_DWORD)v831 || (_DWORD)v15 != 24) )
              {
LABEL_279:
                v4 = a1;
                v7 = v826;
                v13 = v823;
                v10 = 1;
                if ( v122 )
                  v6 += 24;
                goto LABEL_623;
              }
              LODWORD(v831) = 0;
              v156 = sqlite3BtreeNext(*v151, 0);
            }
            v3 = 0;
            Table = v156;
            v14 = v156;
            if ( v156 )
            {
              if ( v156 != 101 )
                goto LABEL_1545;
              v14 = 0;
              Table = 0;
              v130 = 1;
LABEL_278:
              if ( !v130 )
                goto LABEL_279;
LABEL_1218:
              v10 = 1;
              goto LABEL_1219;
            }
LABEL_277:
            v130 = (int)v831;
            goto LABEL_278;
          }
          v133 = v7 + 56LL * *((int *)v6 + 2);
          if ( ((unsigned __int8)v10 & *(_BYTE *)(v7 + 56LL * *((int *)v6 + 1) + 20)) == 0 )
          {
            v134 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), 0);
            v3 = 0;
            if ( (*(_WORD *)(v133 + 20) & 0x9000) != 0 )
            {
              v135 = v134 == 0;
              v136 = v133;
LABEL_243:
              vdbeReleaseAndSetInt64(v136, v135);
              goto LABEL_244;
            }
            *(_QWORD *)v133 = v134 == 0;
            *(_WORD *)(v133 + 20) = 4;
LABEL_951:
            v5 = v825;
            v13 = v823;
LABEL_952:
            v10 = 1;
            goto LABEL_53;
          }
          if ( (*(_WORD *)(v133 + 20) & 0x9000) == 0 )
          {
            *(_WORD *)(v133 + 20) = v10;
            goto LABEL_202;
          }
          v137 = v7 + 56LL * *((int *)v6 + 2);
LABEL_248:
          vdbeMemClearExternAndSetNull(v137);
          goto LABEL_244;
        }
        if ( *((int *)v6 + 1) < 0 )
        {
          LOBYTE(v141) = *((_BYTE *)qword_1800FE430 + (*(_WORD *)(56LL * *((int *)v6 + 3) + v7 + 20) & 0x3F));
        }
        else
        {
          v138 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( *((_DWORD *)v6 + 3) < (int)*(unsigned __int16 *)(v138 + 74) )
          {
            v139 = *(unsigned int *)(v138 + 4LL * *((int *)v6 + 3) + 120);
            if ( (unsigned int)v139 < 0xC )
              v140 = *((unsigned __int8 *)&qword_1800FED70[1] + v139);
            else
              v140 = ((unsigned __int8)v10 & (unsigned __int8)v139) != 0 ? 4 : 8;
            goto LABEL_258;
          }
          v141 = *((_DWORD *)v6 + 4);
        }
        v140 = (_WORD)v10 << (v141 - v10);
LABEL_258:
        v142 = ((unsigned __int16)v140 & *((_WORD *)v6 + 1)) == 0;
        goto LABEL_259;
      }
      if ( (unsigned int)v15 <= 0x22 )
      {
        if ( (_DWORD)v15 != 34 )
        {
          if ( (unsigned int)v15 <= 0x1C )
          {
            if ( (_DWORD)v15 == 28 )
              goto LABEL_269;
            if ( (_DWORD)v15 == 23 || (_DWORD)v15 == 24 )
              goto LABEL_225;
            if ( (_DWORD)v15 != 25 )
            {
              if ( (_DWORD)v15 == 26
                && *(unsigned __int16 *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 12LL) >= *((int *)v6 + 4) )
              {
                goto LABEL_53;
              }
LABEL_269:
              v143 = *((int *)v6 + 1);
              *(_QWORD *)&v837 = 0;
              v144 = v4[15];
              v835 = 0;
              v836 = 0;
              v145 = *(_QWORD *)(v144 + 8 * v143);
              v146 = v7 + 56LL * *((int *)v6 + 3);
              WORD6(v836) = *((_WORD *)v6 + 8);
              *((_QWORD *)&v835 + 1) = v146;
              if ( WORD6(v836) )
              {
                v147 = (int *)(v145 + 36);
                *(_QWORD *)&v835 = *(_QWORD *)(v145 + 56);
                BYTE14(v836) = 0;
                v14 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v145 + 48), &v835, v145 + 36);
                Table = v14;
              }
              else
              {
                if ( (*(_WORD *)(v146 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v146) )
                  goto LABEL_1543;
                v171 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v145 + 56));
                v172 = v171;
                if ( !v171 )
                  goto LABEL_1543;
                sqlite3VdbeRecordUnpack(
                  *(_QWORD *)(v145 + 56),
                  *(unsigned int *)(*((_QWORD *)&v835 + 1) + 16LL),
                  *(_QWORD *)(*((_QWORD *)&v835 + 1) + 8LL),
                  v171);
                *(_BYTE *)(v172 + 30) = 0;
                v147 = (int *)(v145 + 36);
                Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v145 + 48), v172, v145 + 36);
                v14 = Table;
                sqlite3DbFreeNN(v2);
                v9 = v822;
              }
              v3 = 0;
              if ( v14 )
                goto LABEL_1546;
              v173 = *v147;
              *(_BYTE *)(v145 + 3) = 0;
              *(_DWORD *)(v145 + 32) = 0;
              *(_BYTE *)(v145 + 2) = v173 != 0;
              if ( *v6 == 29 )
              {
                v10 = 1;
                if ( !v173 )
                  goto LABEL_1219;
LABEL_335:
                v7 = v826;
                goto LABEL_195;
              }
              if ( v173 )
                goto LABEL_1218;
              v10 = 1;
              if ( *v6 == 27 )
              {
                v174 = 0;
                if ( !WORD6(v836) )
                  goto LABEL_1403;
                while ( (*(_BYTE *)(56LL * v174 + *((_QWORD *)&v835 + 1) + 20) & 1) == 0 )
                {
                  if ( (int)++v174 >= WORD6(v836) )
                    goto LABEL_335;
                }
                goto LABEL_1219;
              }
              v7 = v826;
              v13 = v823;
              if ( *v6 == 26 )
              {
                *(_WORD *)(v145 + 12) = *((_WORD *)v6 + 8);
                goto LABEL_1078;
              }
LABEL_623:
              v5 = v825;
LABEL_978:
              v9 = v822;
              goto LABEL_53;
            }
            v148 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( v148 && !*(_BYTE *)(v148 + 2) )
              goto LABEL_196;
LABEL_504:
            v6 = (unsigned __int8 *)(v5 + 24LL * (*((_DWORD *)v6 + 2) - (int)v10));
            goto LABEL_1310;
          }
          switch ( (_DWORD)v15 )
          {
            case 0x1D:
              goto LABEL_269;
            case 0x1E:
              v163 = 56LL * *((int *)v6 + 3);
              v840 = 0;
              if ( (*(_BYTE *)(v163 + v7 + 20) & 0x24) == 0 )
              {
                LOBYTE(v5) = v9;
                LOBYTE(v13) = 67;
                v164 = *(_OWORD *)(v163 + v7 + 16);
                v844 = *(_OWORD *)(v163 + v7);
                v165 = *(_OWORD *)(v163 + v7 + 32);
                v845 = v164;
                *(_QWORD *)&v164 = *(_QWORD *)(v163 + v7 + 48);
                v846 = v165;
                v847 = v164;
                applyAffinity(&v844, v13, v5);
                v3 = 0;
                if ( (BYTE4(v845) & 4) == 0 )
                  goto LABEL_1218;
                v166 = v844;
                goto LABEL_322;
              }
              break;
            case 0x1F:
              break;
            case 0x20:
LABEL_1211:
              v635 = *((int *)v6 + 1);
              v636 = v4[15];
              LODWORD(v829) = 0;
              v637 = *(_QWORD *)(v636 + 8 * v635);
              v638 = *(_QWORD *)(v637 + 48);
              if ( (_BYTE)v15 == 0x89 )
              {
                v639 = *(_QWORD *)(v637 + 48);
                *(_DWORD *)(v637 + 36) = -1;
                IsValidNN = sqlite3BtreeCursorIsValidNN(v639);
                v3 = 0;
                if ( IsValidNN )
                  goto LABEL_1407;
              }
              v641 = sqlite3BtreeLast(v638, &v829);
              v3 = 0;
              Table = v641;
              v14 = v641;
              *(_BYTE *)(v637 + 2) = v829;
              *(_BYTE *)(v637 + 3) = 0;
              *(_DWORD *)(v637 + 32) = 0;
              if ( v641 )
                goto LABEL_1546;
              if ( *((int *)v6 + 2) <= 0 )
                goto LABEL_1407;
              if ( (_DWORD)v829 )
                goto LABEL_1218;
              goto LABEL_79;
            default:
              v157 = *((int *)v6 + 1);
              v158 = v4[15];
              LODWORD(v829) = 0;
              v159 = *(_QWORD *)(*(_QWORD *)(v158 + 8 * v157) + 48LL);
              v160 = sqlite3BtreeFirst(v159, &v829);
              v3 = 0;
              Table = v160;
              v14 = v160;
              if ( v160 )
                goto LABEL_1546;
              if ( (_DWORD)v829 )
              {
                v161 = -1;
              }
              else
              {
                v162 = sqlite3BtreeRowCountEst(v159);
                v161 = (__int16)sqlite3LogEst(v162);
                v3 = 0;
              }
              v10 = 1;
              if ( v161 < *((int *)v6 + 3) )
                goto LABEL_1404;
              if ( v161 > *((int *)v6 + 4) )
                goto LABEL_195;
              goto LABEL_1219;
          }
          v166 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
LABEL_322:
          v167 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v168 = *(_QWORD *)(v167 + 48);
          v840 = 0;
          v169 = sqlite3BtreeTableMoveto(v168, v166, 0, &v840);
          v3 = 0;
          *(_QWORD *)(v167 + 80) = v166;
          *(_WORD *)(v167 + 2) = 0;
          v14 = v169;
          *(_DWORD *)(v167 + 32) = 0;
          Table = v169;
          *(_DWORD *)(v167 + 36) = v840;
          if ( v840 )
          {
            if ( *((_DWORD *)v6 + 2) )
              goto LABEL_1218;
            v14 = sqlite3CorruptError(98846);
            Table = v14;
            v3 = 0;
          }
          goto LABEL_325;
        }
        goto LABEL_358;
      }
      if ( (unsigned int)v15 > 0x28 )
      {
        if ( (_DWORD)v15 != 41 && (_DWORD)v15 != 42 )
        {
          if ( (unsigned int)(v15 - 43) > 1 )
            goto LABEL_53;
          v185 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), 2);
          v186 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 2), 2);
          v10 = 1;
          v187 = v186 + 2 * v185 + v185;
          v188 = &qword_1800FA4F0;
          if ( *v6 != 44 )
            v188 = &qword_1800FB630;
          v189 = *((unsigned __int8 *)v188 + v187);
          v190 = 56LL * *((int *)v6 + 3);
          v191 = *(_WORD *)(v190 + v7 + 20);
          if ( (_BYTE)v189 == 2 )
          {
            v192 = v191 & 0xF240 | 1;
          }
          else
          {
            *(_QWORD *)(v190 + v7) = v189;
            v192 = v191 & 0xF240 | 4;
          }
          *(_WORD *)(v190 + v7 + 20) = v192;
          goto LABEL_60;
        }
      }
      else if ( (_DWORD)v15 != 40 )
      {
        v175 = v15 - 35;
        if ( !v175 )
        {
LABEL_358:
          *((_DWORD *)v4 + 55) += v10;
          goto LABEL_359;
        }
        v176 = v175 - 1;
        if ( !v176 )
        {
LABEL_359:
          v181 = *((int *)v6 + 1);
          v182 = v4[15];
          LODWORD(v831) = 0;
          v183 = *(_QWORD *)(v182 + 8 * v181);
          LODWORD(v831) = v10;
          if ( *(_BYTE *)v183 == (_BYTE)v10 )
          {
            v184 = sqlite3VdbeSorterRewind(v183, &v831);
            v3 = 0;
          }
          else
          {
            v184 = sqlite3BtreeFirst(*(_QWORD *)(v183 + 48), &v831);
            v3 = 0;
            *(_BYTE *)(v183 + 3) = 0;
            *(_DWORD *)(v183 + 32) = 0;
          }
          Table = v184;
          v14 = v184;
          if ( v184 )
            goto LABEL_1546;
          *(_BYTE *)(v183 + 2) = (_BYTE)v831;
          if ( *((int *)v6 + 2) <= 0 )
            goto LABEL_1408;
          v105 = (_DWORD)v831 == 0;
LABEL_194:
          v10 = 1;
          if ( v105 )
          {
LABEL_195:
            v5 = v825;
            goto LABEL_196;
          }
LABEL_1219:
          v9 = v822;
          goto LABEL_214;
        }
        v177 = v176 - 1;
        if ( v177 )
        {
          v178 = v177 - 1;
          if ( v178 )
          {
            if ( v178 != 1 )
              goto LABEL_53;
            v179 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v180 = sqlite3BtreeNext(*(_QWORD *)(v179 + 48), *((unsigned int *)v6 + 3));
          }
          else
          {
            v179 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v180 = sqlite3BtreePrevious(*(_QWORD *)(v179 + 48), *((unsigned int *)v6 + 3));
          }
        }
        else
        {
          v179 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v180 = sqlite3VdbeSorterNext(v2, v179);
        }
        v14 = v180;
        Table = v180;
        v3 = 0;
        *(_DWORD *)(v179 + 32) = 0;
        if ( !v180 )
        {
          *(_BYTE *)(v179 + 2) = 0;
          v10 = 1;
          ++*((_DWORD *)v4 + *((unsigned __int16 *)v6 + 1) + 53);
LABEL_503:
          v5 = v825;
          goto LABEL_504;
        }
        if ( v180 != 101 )
          goto LABEL_1546;
        v10 = 1;
        Table = 0;
        *(_BYTE *)(v179 + 2) = 1;
        v14 = 0;
LABEL_1310:
        if ( *(_DWORD *)(v2 + 408) )
        {
LABEL_1536:
          v14 = 9;
          goto LABEL_1546;
        }
        v713 = v842;
        if ( v843 >= v842 )
        {
          while ( 1 )
          {
            v714 = *(__int64 (__fastcall **)(_QWORD))(v2 + 528);
            if ( !v714 )
              goto LABEL_1407;
            v715 = *(unsigned int *)(v2 + 544);
            v716 = v714(*(_QWORD *)(v2 + 536));
            v3 = 0;
            if ( v716 )
              goto LABEL_1535;
            v713 += v715;
            v842 = v713;
            if ( v843 < v713 )
              goto LABEL_51;
          }
        }
LABEL_1403:
        v7 = v826;
LABEL_1404:
        v13 = v823;
        goto LABEL_623;
      }
    }
    v193 = *((int *)v6 + 1);
    *(_QWORD *)&v837 = 0;
    v194 = v4[15];
    v835 = 0;
    v836 = 0;
    v195 = *(_QWORD *)(v194 + 8 * v193);
    v844 = 0;
    v845 = 0;
    *(_QWORD *)&v835 = *(_QWORD *)(v195 + 56);
    WORD6(v836) = *((_WORD *)v6 + 8);
    BYTE14(v836) = -((unsigned __int8)v15 < 0x2Au);
    v196 = 56LL * *((int *)v6 + 3);
    v846 = 0;
    v847 = 0;
    *((_QWORD *)&v835 + 1) = v7 + v196;
    v197 = *(_QWORD *)(v195 + 48);
    v198 = sqlite3BtreePayloadSize(v197);
    if ( v198 - 1 <= 0x7FFFFFFE )
    {
      sqlite3VdbeMemInit(&v844, v2, 0);
      v199 = sqlite3VdbeMemFromBtreeZeroOffset(v197, v198, &v844);
      v3 = 0;
      Table = v199;
      v14 = v199;
      if ( v199 )
        goto LABEL_1546;
      v200 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v845, *((_QWORD *)&v844 + 1), &v835, 0);
      sqlite3VdbeMemReleaseMalloc(&v844);
      v201 = v200 + 1;
      v3 = 0;
      v202 = -v200;
      v10 = 1;
      if ( (*v6 & 1) != 0 )
        v202 = v201;
      if ( v202 <= 0 )
        goto LABEL_146;
      goto LABEL_1219;
    }
    v811 = sqlite3CorruptError(100143);
LABEL_1530:
    v14 = v811;
    goto LABEL_1523;
  }
  if ( (unsigned int)v15 <= 0x44 )
  {
    if ( (_DWORD)v15 == 68 )
    {
      v276 = 56LL * *((int *)v6 + 1);
      v277 = 3LL * *(_QWORD *)(v276 + v7);
      *(_QWORD *)(v276 + v7) = (int)(-1431655765 * ((__int64)&v6[-v4[17]] >> 3) - v10);
      v118 = 3LL * (*(_DWORD *)(v5 + 8 * v277 + 8) - (int)v10);
      goto LABEL_219;
    }
    if ( (unsigned int)v15 > 0x39 )
    {
      if ( (unsigned int)v15 > 0x3F )
      {
        v262 = v15 - 64;
        if ( !v262 )
        {
          v271 = 56LL * *((int *)v6 + 1);
          v272 = filterHash(v7, v6);
          v10 = 1;
          v273 = v272 % (8 * *(_DWORD *)(v271 + v7 + 16));
          v274 = *(char *)((v273 >> 3) + *(_QWORD *)(v271 + v7 + 8));
          v275 = _bittest(&v274, v273 & 7);
          v5 = v825;
          if ( v275 )
          {
            ++*((_DWORD *)v4 + 60);
            goto LABEL_61;
          }
          ++*((_DWORD *)v4 + 61);
          v3 = 0;
          goto LABEL_215;
        }
        v263 = v262 - 1;
        if ( v263 )
        {
          v264 = v263 - 1;
          if ( v264 )
          {
            if ( v264 != 1 )
              goto LABEL_53;
            v265 = 56LL * *((int *)v6 + 1);
            if ( (*(_BYTE *)(v265 + v7 + 20) & 4) == 0 )
              goto LABEL_53;
            v113 = *(_QWORD *)(v265 + v7);
            goto LABEL_206;
          }
        }
        v266 = *((_QWORD *)v6 + 2);
        v267 = v7 + 56LL * *((int *)v6 + 3);
        if ( *(_QWORD *)v266 != v267 )
        {
          v268 = *(unsigned __int8 *)(v266 + 42);
          *(_BYTE *)(v266 + 40) = v822;
          *(_QWORD *)(v266 + 24) = v4;
          *(_QWORD *)v266 = v267;
          while ( 1 )
          {
            v268 -= v10;
            if ( v268 < 0 )
              break;
            *(_QWORD *)(v266 + 8LL * (unsigned int)v268 + 48) = v7 + 56LL * (v268 + *((_DWORD *)v6 + 2));
          }
        }
        *(_WORD *)(v267 + 20) &= 0xF241u;
        *(_WORD *)(v267 + 20) |= v10;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v266 + 8) + 24LL))(
          v266,
          *(unsigned __int8 *)(v266 + 42),
          v266 + 48);
        v269 = *(_DWORD *)(v266 + 36);
        v3 = 0;
        if ( !v269 )
          goto LABEL_1408;
        if ( v269 > 0 )
        {
          v270 = (const char *)sqlite3_value_text(v267);
          sqlite3VdbeError(v4, "%s", v270);
          v14 = *(_DWORD *)(v266 + 36);
          Table = v14;
        }
        sqlite3VdbeDeleteAuxData(v2, v4 + 37, *(unsigned int *)(v266 + 32), *((unsigned int *)v6 + 1));
        v3 = 0;
        *(_DWORD *)(v266 + 36) = 0;
LABEL_325:
        v170 = v14 == 0;
        goto LABEL_326;
      }
      if ( (_DWORD)v15 != 63 )
      {
        v245 = v15 - 58;
        if ( v245 )
        {
          v246 = v245 - 1;
          if ( !v246 )
          {
            v255 = 56LL * *((int *)v6 + 1);
            v256 = *(_QWORD *)(v255 + v7);
            if ( v256 <= 0 )
              goto LABEL_196;
            *(_QWORD *)(v255 + v7) = v256 - *((int *)v6 + 3);
            goto LABEL_215;
          }
          v247 = v246 - 1;
          if ( !v247 )
          {
            v253 = 56LL * *((int *)v6 + 1);
            v254 = *(_QWORD *)(v253 + v7);
            if ( !v254 )
              goto LABEL_53;
            if ( v254 > 0 )
              *(_QWORD *)(v253 + v7) = v254 - 1;
            goto LABEL_215;
          }
          v248 = v247 - 1;
          if ( !v248 )
          {
            v250 = 56LL * *((int *)v6 + 1);
            v251 = *(_QWORD *)(v250 + v7);
            if ( v251 == 0x8000000000000000uLL )
              goto LABEL_53;
            v252 = v251 - 1;
            *(_QWORD *)(v250 + v7) = v252;
            if ( v252 )
              goto LABEL_53;
            goto LABEL_1219;
          }
          if ( v248 != 1 )
            goto LABEL_53;
          v249 = sqlite3BtreeIncrVacuum(*(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8));
          v3 = 0;
          Table = v249;
          v14 = v249;
          if ( !v249 )
            goto LABEL_1408;
          if ( v249 != 101 )
            goto LABEL_1546;
          v14 = 0;
          Table = 0;
          goto LABEL_213;
        }
        v208 = (_DWORD)v13 == 0;
        goto LABEL_497;
      }
      v257 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
      if ( *(_BYTE *)(v257 + 2) )
        goto LABEL_148;
      v258 = *(__int64 ***)(v257 + 48);
      v259 = *v258;
      v260 = **v258;
      Table = (*(__int64 (**)(void))(v260 + 72))();
      v14 = Table;
      sqlite3VtabImportErrmsg(v4, v259);
      v3 = 0;
      if ( Table )
        goto LABEL_1546;
      v261 = (*(__int64 (__fastcall **)(_QWORD))(v260 + 80))(*(_QWORD *)(v257 + 48));
      v9 = v822;
      v3 = 0;
      if ( v261 )
      {
LABEL_1309:
        v10 = 1;
        goto LABEL_1310;
      }
      goto LABEL_502;
    }
    if ( (_DWORD)v15 != 57 )
    {
      if ( (unsigned int)v15 <= 0x33 )
      {
        if ( (_DWORD)v15 == 51 )
        {
          if ( ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 1) + v7 + 20)) != 0 )
            goto LABEL_53;
          goto LABEL_215;
        }
        v203 = v15 - 46;
        if ( v203 )
        {
          v204 = v203 - 1;
          if ( v204 )
          {
            v205 = v204 - 1;
            if ( v205 )
            {
              v206 = v205 - 1;
              if ( v206 )
              {
                if ( v206 != 1 )
                  goto LABEL_53;
                v142 = ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 1) + v7 + 20)) == 0;
LABEL_259:
                if ( v142 )
                  goto LABEL_53;
                goto LABEL_215;
              }
              if ( *((_DWORD *)v6 + 1) )
                v207 = *(_QWORD *)(v2 + 760) == 0;
              else
                v207 = v4[10] == 0;
              if ( !v207 )
                goto LABEL_53;
              v208 = *(_QWORD *)(v2 + 768) == 0;
LABEL_497:
              if ( !v208 )
                goto LABEL_53;
              goto LABEL_215;
            }
            v209 = *((_QWORD *)v6 + 2);
            v828 = (unsigned int *)v209;
            if ( *((_WORD *)v6 + 1) )
            {
              for ( jj = v4[33]; jj; jj = *(_QWORD *)(jj + 8) )
              {
                if ( *(_QWORD *)(jj + 48) == *(_QWORD *)(v209 + 32) )
                  goto LABEL_202;
              }
            }
            if ( *((_DWORD *)v4 + 70) >= *(_DWORD *)(v2 + 176) )
            {
              v14 = v10;
              sqlite3VdbeError(v4, "too many levels of trigger recursion");
              goto LABEL_1523;
            }
            v211 = (int *)(v209 + 16);
            v212 = (int *)(v209 + 8);
            v213 = 56LL * *((int *)v6 + 3) + v7;
            if ( (*(_BYTE *)(v213 + 20) & 0x10) != 0 )
            {
              v216 = *(_QWORD *)(v213 + 8);
              v218 = (__int64 *)v209;
LABEL_413:
              *((_DWORD *)v4 + 70) += v10;
              *(_QWORD *)(v216 + 8) = v4[33];
              v826 = v216 + 112;
              *(_QWORD *)(v216 + 56) = *(_QWORD *)(v830 + 56);
              *(_QWORD *)(v216 + 96) = v4[7];
              *(_QWORD *)(v216 + 104) = *(_QWORD *)(*v4 + 120);
              *(_QWORD *)(v216 + 64) = v4[37];
              v4[13] = v216 + 112;
              v4[37] = 0;
              v4[7] = 0;
              v4[33] = v216;
              v221 = *(int *)(v216 + 88);
              *((_DWORD *)v4 + 9) = v221;
              *((_DWORD *)v4 + 10) = *(unsigned __int16 *)(v216 + 92);
              v4[15] = v216 + 112 + 56 * v221;
              v222 = (void *)(v216 + 112 + 8 * (*v211 + 7 * v221));
              *(_QWORD *)(v216 + 40) = v222;
              memset_0(v222, 0, (*v212 + 7) / 8);
              v223 = *v218;
              v14 = Table;
              v4[17] = *v218;
              v224 = *v212;
              v2 = v830;
              v6 = (unsigned __int8 *)(v223 - 24);
              v825 = v223;
              *((_DWORD *)v4 + 36) = v224;
LABEL_1308:
              v3 = 0;
              goto LABEL_1309;
            }
            v214 = *v211 + *(_DWORD *)(v209 + 12) + 1;
            if ( *v211 )
              v214 = *v211 + *(_DWORD *)(v209 + 12);
            v215 = (*v212 + 7) / 8 + 8 * (*v211 + 7 * (v214 + 2));
            v216 = sqlite3DbMallocZero(v830, v215);
            if ( v216 )
            {
              sqlite3VdbeMemRelease(v213);
              *(_QWORD *)(v213 + 48) = sqlite3VdbeFrameMemDel;
              v217 = v216 + 112;
              *(_DWORD *)(v213 + 16) = v215;
              v4 = a1;
              *(_WORD *)(v213 + 20) = 4112;
              *(_QWORD *)(v213 + 8) = v216;
              v218 = (__int64 *)v828;
              *(_QWORD *)v216 = a1;
              *(_DWORD *)(v216 + 88) = v214;
              *(_DWORD *)(v216 + 92) = *v211;
              *(_DWORD *)(v216 + 76) = -1431655765 * ((__int64)&v6[-v825] >> 3);
              *(_QWORD *)(v216 + 24) = a1[13];
              *(_DWORD *)(v216 + 84) = *((_DWORD *)a1 + 9);
              *(_QWORD *)(v216 + 32) = a1[15];
              *(_DWORD *)(v216 + 72) = *((_DWORD *)a1 + 10);
              *(_QWORD *)(v216 + 16) = a1[17];
              *(_DWORD *)(v216 + 80) = *((_DWORD *)a1 + 36);
              *(_QWORD *)(v216 + 48) = v218[4];
              v219 = v216 + 56 * (v214 + 2LL);
              if ( v216 + 112 != v219 )
              {
                v220 = v830;
                do
                {
                  *(_WORD *)(v217 + 20) = 0;
                  *(_QWORD *)(v217 + 24) = v220;
                  v217 += 56;
                }
                while ( v217 != v219 );
                v4 = a1;
              }
              v9 = v822;
              LODWORD(v10) = 1;
              goto LABEL_413;
            }
            goto LABEL_1541;
          }
          v225 = *((_DWORD *)v6 + 4);
          v226 = v7 + 56LL * *((int *)v6 + 1);
          v227 = *((int *)v6 + 3);
          if ( (*(_BYTE *)(v226 + 20) & 0x10) == 0 )
          {
            v228 = sqlite3VdbeMemSetRowSet(v226);
            v3 = 0;
            if ( v228 )
              goto LABEL_1543;
          }
          v229 = 56 * v227;
          v230 = v225 < 0;
          if ( v225 )
          {
            v231 = sqlite3RowSetTest(*(_QWORD *)(v226 + 8), (unsigned int)v225, *(_QWORD *)(v229 + v826));
            v3 = 0;
            if ( v231 )
              goto LABEL_1218;
            v230 = v225 < 0;
          }
          if ( v230 )
          {
LABEL_79:
            v7 = v826;
            goto LABEL_80;
          }
          sqlite3RowSetInsert(*(_QWORD *)(v226 + 8), *(_QWORD *)(v229 + v826));
LABEL_421:
          v7 = v826;
          goto LABEL_422;
        }
        v232 = *((int *)v6 + 1);
        v828 = 0;
        v233 = v7 + 56 * v232;
        if ( (*(_BYTE *)(v233 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v233 + 8), &v828) )
        {
          sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 + 3), v828);
          goto LABEL_1308;
        }
        sqlite3VdbeMemSetNull(v233);
        v3 = 0;
LABEL_502:
        v10 = 1;
        goto LABEL_503;
      }
      if ( (_DWORD)v15 != 52 && (_DWORD)v15 != 53 && (_DWORD)v15 != 54 && (unsigned int)(v15 - 55) > 1 )
        goto LABEL_53;
    }
    v234 = v7 + 56LL * *((int *)v6 + 1);
    v235 = v7 + 56LL * *((int *)v6 + 3);
    v236 = *(_WORD *)(v234 + 20);
    v237 = *(_WORD *)(v235 + 20);
    if ( ((unsigned __int8)v236 & (unsigned __int8)v237 & 4) != 0 )
    {
      if ( *(_QWORD *)v235 <= *(_QWORD *)v234 )
      {
        v239 = *v6;
        v9 = v822;
        if ( *(_QWORD *)v235 >= *(_QWORD *)v234 )
        {
          if ( *((_BYTE *)&qword_1800FBAB0[26] + v239 + 2) )
            goto LABEL_215;
          v13 = 0;
        }
        else
        {
          if ( *((_BYTE *)&qword_1800FBAB0[25] + v239 + 4) )
            goto LABEL_215;
          v13 = 0xFFFFFFFFLL;
        }
        goto LABEL_438;
      }
      v238 = *((_BYTE *)&qword_1800FBAB0[27] + v15) == 0;
LABEL_436:
      v9 = v822;
      if ( !v238 )
        goto LABEL_215;
      v13 = (unsigned int)v10;
LABEL_438:
      v4 = a1;
      v7 = v826;
      v823 = v13;
      goto LABEL_53;
    }
    v240 = v236 | v237;
    if ( ((unsigned __int8)(v236 | v237) & (unsigned __int8)v10) != 0 )
    {
      if ( (v6[2] & 0x80u) == 0 )
      {
        v238 = (v6[2] & 0x10) == 0;
        goto LABEL_436;
      }
      if ( ((unsigned __int8)(v236 & v237) & (unsigned __int8)v10) != 0 && (v237 & 0x100) == 0 )
      {
        v13 = 0;
LABEL_449:
        v823 = v13;
LABEL_450:
        v241 = *v6;
        if ( (_DWORD)v13 )
          v242 = *((_BYTE *)&qword_1800FBAB0[27] + v241);
        else
          v242 = *((_BYTE *)&qword_1800FBAB0[26] + v241 + 2);
LABEL_476:
        *(_WORD *)(v235 + 20) = v237;
        *(_WORD *)(v234 + 20) = v236;
        if ( !v242 )
        {
          v4 = a1;
          v7 = v826;
          goto LABEL_148;
        }
        goto LABEL_1219;
      }
      if ( ((unsigned __int8)v237 & (unsigned __int8)v10) == 0 )
      {
        v13 = (unsigned int)v10;
        goto LABEL_449;
      }
      v13 = 0xFFFFFFFFLL;
      v823 = -1;
    }
    else
    {
      v243 = v6[2] & 0x47;
      if ( v243 < 0x43u )
      {
        if ( v243 == 66 && (v240 & 2) != 0 )
        {
          if ( (v236 & 2) != 0 )
          {
            *(_WORD *)(v234 + 20) = v236 & 0xFFD3;
          }
          else if ( (v236 & 0x2C) != 0 )
          {
            LOBYTE(v5) = v10;
            LOBYTE(v13) = v822;
            sqlite3VdbeMemStringify(v234, v13, v5);
            v236 = *(_WORD *)(v234 + 20) ^ (*(_WORD *)(v234 + 20) ^ v236) & 0xDBF;
            LOBYTE(v10) = 1;
            if ( v234 == v235 )
              v237 = v236 | 2;
          }
          if ( (v237 & 2) != 0 )
          {
            *(_WORD *)(v235 + 20) &= 0xFFD3u;
          }
          else if ( (v237 & 0x2C) != 0 )
          {
            LOBYTE(v5) = v10;
            LOBYTE(v13) = v822;
            sqlite3VdbeMemStringify(v235, v13, v5);
            v237 = *(_WORD *)(v235 + 20) ^ (*(_WORD *)(v235 + 20) ^ v237) & 0xDBF;
          }
        }
      }
      else if ( (v240 & 2) != 0 )
      {
        if ( (v236 & 0x2E) == 2 )
        {
          applyNumericAffinity(v234, 0);
          v237 = *(_WORD *)(v235 + 20);
        }
        if ( (v237 & 0x2E) == 2 )
          applyNumericAffinity(v235, 0);
      }
      v244 = sqlite3MemCompare(v235, v234, *((_QWORD *)v6 + 2));
      v5 = v825;
      v3 = 0;
      v823 = v244;
      v13 = (unsigned int)v244;
      v10 = 1;
      if ( v244 >= 0 )
        goto LABEL_450;
    }
    v242 = *((_BYTE *)&qword_1800FBAB0[25] + *v6 + 4);
    goto LABEL_476;
  }
  if ( (unsigned int)v15 > 0x50 )
  {
    if ( (unsigned int)v15 > 0x56 )
    {
      v324 = v15 - 87;
      if ( !v324 )
      {
        if ( (*(_BYTE *)(v7 + 56LL * *((int *)v6 + 1) + 20) & 0x24) == 0 )
          goto LABEL_53;
        sqlite3VdbeMemRealify();
        goto LABEL_244;
      }
      v325 = v324 - 1;
      if ( v325 )
      {
        v326 = v325 - 2;
        if ( !v326 )
        {
          if ( ((unsigned __int8)v10 & v6[2]) != 0 )
            v327 = *((_QWORD *)v6 - 1) + 4LL;
          else
            v327 = 0;
          v328 = *((_DWORD *)v6 + 3);
          v329 = 0;
          v330 = (unsigned int *)*((_QWORD *)v6 + 2);
          v331 = *((_DWORD *)v6 + 1);
          v332 = *((_DWORD *)v6 + 2);
          v828 = v330;
          LODWORD(v829) = v328;
          v834 = v331;
          LODWORD(v831) = v332;
          if ( v328 <= 0 )
            goto LABEL_616;
          while ( 1 )
          {
            v333 = v327 ? *(_DWORD *)(v327 + 4LL * v329) : v329;
            v334 = v826 + 56LL * (unsigned int)(v333 + v332);
            v335 = (unsigned __int8)(v10 & *(_BYTE *)(*((_QWORD *)v330 + 3) + v329));
            v336 = v826 + 56LL * (v333 + v331);
            v337 = sqlite3MemCompare(v336, v334, *(_QWORD *)&v330[2 * v329 + 8]);
            v3 = 0;
            v823 = v337;
            v13 = v337;
            v10 = 1;
            if ( v337 )
              break;
            v330 = v828;
            ++v329;
            v331 = v834;
            v332 = (int)v831;
            if ( (int)v329 >= (int)v829 )
            {
              v14 = Table;
              v4 = a1;
LABEL_616:
              v7 = v826;
              v5 = v825;
              goto LABEL_148;
            }
          }
          if ( (*(_BYTE *)(v329 + *((_QWORD *)v828 + 3)) & 2) != 0
            && ((*(_BYTE *)(v336 + 20) & 1) != 0 || (*(_BYTE *)(v334 + 20) & 1) != 0) )
          {
            v13 = -v337;
            v823 = -v337;
          }
          v14 = Table;
          v4 = a1;
          v7 = v826;
          if ( v335 )
          {
            v13 = (unsigned int)-(int)v13;
            v823 = v13;
          }
          goto LABEL_623;
        }
        if ( v326 != 1 )
          goto LABEL_53;
        v135 = (int)sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((unsigned int *)v6 + 3))
             ^ (unsigned __int64)*((int *)v6 + 4);
        v319 = v7 + 56LL * *((int *)v6 + 2);
        if ( (*(_WORD *)(v319 + 20) & 0x9000) == 0 )
        {
          *(_QWORD *)v319 = v135;
          *(_WORD *)(v319 + 20) = 4;
          v3 = 0;
          goto LABEL_951;
        }
LABEL_591:
        v136 = v319;
        goto LABEL_243;
      }
      v338 = v7 + 56LL * *((int *)v6 + 1);
      if ( (*(_WORD *)(v338 + 20) & 0x400) != 0 )
      {
        v339 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 1));
        v3 = 0;
        v14 = v339;
        if ( v339 )
          goto LABEL_1546;
      }
      LOBYTE(v13) = v6[8];
      LOBYTE(v5) = v9;
      v71 = sqlite3VdbeMemCast(v338, v13, v5);
      goto LABEL_153;
    }
    if ( (_DWORD)v15 == 86 )
    {
      v323 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 1));
      sqlite3VdbeMemIntegerify(v323);
      *v323 += *((int *)v6 + 2);
      goto LABEL_244;
    }
    v314 = v15 - 81;
    if ( v314 )
    {
      v315 = v314 - 1;
      if ( v315 )
      {
        v316 = v315 - 1;
        if ( v316 )
        {
          v317 = v316 - 1;
          if ( !v317 )
          {
            *((_DWORD *)v4 + 11) = v10 | (*((_DWORD *)v4 + 11) + 2);
            v4[20] = v7 + 56LL * *((int *)v6 + 1);
            if ( !*(_BYTE *)(v2 + 103) )
            {
              if ( (*(_BYTE *)(v2 + 110) & 4) != 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v2 + 248))(4, *(_QWORD *)(v2 + 256), v4, 0);
                v5 = v825;
                LODWORD(v10) = 1;
              }
              v14 = 100;
              *((_DWORD *)v4 + 12) = v10 - 1431655765 * ((__int64)&v6[-v5] >> 3);
              goto LABEL_1564;
            }
            goto LABEL_1543;
          }
          if ( v317 != 1 || !*((_DWORD *)v6 + 1) )
            goto LABEL_53;
          v318 = *((int *)v6 + 1);
LABEL_589:
          v319 = v7 + 56 * v318;
          if ( (*(_WORD *)(v319 + 20) & 0x9000) == 0 )
          {
            *(_QWORD *)v319 = 0;
            *(_WORD *)(v319 + 20) = 4;
            goto LABEL_53;
          }
          v135 = 0;
          goto LABEL_591;
        }
        v71 = sqlite3VdbeCheckFk(v4, 0);
LABEL_153:
        v3 = 0;
        Table = v71;
        v72 = v71 == 0;
        v14 = v71;
        goto LABEL_154;
      }
      v320 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v320 + 20) & 0x9000) != 0 )
      {
        v135 = *(_QWORD *)(56LL * *((int *)v6 + 1) + v7);
        v136 = v7 + 56LL * *((int *)v6 + 2);
        goto LABEL_243;
      }
      *(_QWORD *)v320 = *(_QWORD *)(56LL * *((int *)v6 + 1) + v7);
      *(_WORD *)(v320 + 20) = 4;
LABEL_1078:
      v5 = v825;
      goto LABEL_53;
    }
    v321 = v7 + 56LL * *((int *)v6 + 1);
    v322 = v7 + 56LL * *((int *)v6 + 2);
LABEL_598:
    sqlite3VdbeMemShallowCopy(v322, v321, 0x4000);
    goto LABEL_244;
  }
  if ( (_DWORD)v15 == 80 )
  {
    v309 = *((_DWORD *)v6 + 3);
    v310 = v826 + 56LL * *((int *)v6 + 1);
    for ( kk = v826 + 56LL * *((int *)v6 + 2); ; kk += 56 )
    {
      sqlite3VdbeMemShallowCopy(kk, v310, 0x4000);
      if ( (*(_WORD *)(kk + 20) & 0x4000) != 0 )
      {
        v312 = sqlite3VdbeMemMakeWriteable(kk);
        v3 = 0;
        if ( v312 )
          goto LABEL_1543;
      }
      else
      {
        v3 = 0;
      }
      v313 = *(_WORD *)(kk + 20);
      if ( (v313 & 0x800) != 0 && (v6[2] & 2) != 0 )
        *(_WORD *)(kk + 20) = v313 & 0xF7FF;
      if ( !v309 )
        break;
      --v309;
      v310 += 56;
    }
    goto LABEL_1407;
  }
  if ( (unsigned int)v15 > 0x4A )
  {
    v289 = v15 - 75;
    if ( v289 )
    {
      v290 = v289 - 1;
      if ( !v290 )
      {
        v304 = 56LL * *((int *)v6 + 1);
        *(_WORD *)(v304 + v7 + 20) &= 0xFFC1u;
        *(_WORD *)(v304 + v7 + 20) |= v10;
        goto LABEL_53;
      }
      v291 = v290 - 1;
      if ( v291 )
      {
        v292 = v291 - 1;
        if ( v292 )
        {
          if ( v292 != 1 )
            goto LABEL_53;
          v293 = *((_DWORD *)v6 + 3);
          v294 = v826 + 56LL * *((int *)v6 + 1);
          v295 = v826 + 56LL * *((int *)v6 + 2);
          while ( 1 )
          {
            sqlite3VdbeMemMove(v295, v294);
            if ( (*(_WORD *)(v295 + 20) & 0x4000) != 0 )
            {
              v296 = sqlite3VdbeMemMakeWriteable(v295);
              v3 = 0;
              if ( v296 )
                goto LABEL_1543;
            }
            else
            {
              v3 = 0;
            }
            v294 += 56;
            v295 += 56;
            v10 = 1;
            if ( !--v293 )
              goto LABEL_145;
          }
        }
        v297 = 56LL * *((int *)v6 + 1) - 56 + v4[16];
        v298 = sqlite3VdbeMemTooBig(v297);
        v3 = 0;
        if ( v298 )
          goto LABEL_1528;
        v299 = v7 + 56LL * *((int *)v6 + 2);
        if ( (*(_WORD *)(v299 + 20) & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 2));
          v3 = 0;
        }
        *(_OWORD *)v299 = *(_OWORD *)v297;
        *(_QWORD *)(v299 + 16) = *(_QWORD *)(v297 + 16);
        *(_WORD *)(v299 + 20) = *(_WORD *)(v299 + 20) & 0x8FBF | 0x2040;
        goto LABEL_80;
      }
      v300 = out2Prerelease(v4, v6);
      v301 = *((_QWORD *)v6 + 2);
      v302 = v300;
      if ( v301 )
      {
        sqlite3VdbeMemSetStr(v300, v301, *((int *)v6 + 1), 0, 0);
        v3 = 0;
      }
      else
      {
        sqlite3VdbeMemSetZeroBlob(v300, *((unsigned int *)v6 + 1));
        v303 = sqlite3VdbeMemExpandBlob(v302);
        v3 = 0;
        if ( v303 )
          goto LABEL_1543;
      }
      *(_BYTE *)(v302 + 22) = v9;
      goto LABEL_52;
    }
LABEL_565:
    v305 = out2Prerelease(v4, v6);
    v306 = *((_DWORD *)v6 + 3) - *((_DWORD *)v6 + 2);
    v10 = 1;
    v3 = 0;
    v307 = *((_DWORD *)v6 + 1) != 0 ? 0x100 : 0;
    *(_DWORD *)(v305 + 16) = 0;
    v308 = v307 + 1;
    *(_WORD *)(v305 + 20) = v308;
    if ( v306 > 0 )
    {
      do
      {
        v305 += 56;
        if ( (*(_WORD *)(v305 + 20) & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v305);
          v3 = 0;
          v10 = 1;
        }
        --v306;
        *(_WORD *)(v305 + 20) = v308;
        *(_DWORD *)(v305 + 16) = 0;
      }
      while ( v306 > 0 );
      goto LABEL_145;
    }
    goto LABEL_1403;
  }
  if ( (_DWORD)v15 == 74 )
    goto LABEL_565;
  v278 = v15 - 69;
  if ( v278 )
  {
    v279 = v278 - 1;
    if ( v279 )
    {
      v280 = v279 - 1;
      if ( v280 )
      {
        v281 = v280 - 1;
        if ( v281 )
        {
          if ( v281 != 1 )
            goto LABEL_53;
          goto LABEL_1075;
        }
        v282 = out2Prerelease(v4, v6);
LABEL_534:
        *(_QWORD *)v282 = **((_QWORD **)v6 + 2);
        goto LABEL_244;
      }
      v283 = (unsigned int **)out2Prerelease(v4, v6);
      v284 = (unsigned int *)*((int *)v6 + 1);
LABEL_536:
      *v283 = v284;
      goto LABEL_244;
    }
  }
  else if ( ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 3) + v7 + 20)) == 0 )
  {
    goto LABEL_53;
  }
  v285 = v4[33];
  if ( v285 && !*((_DWORD *)v6 + 1) )
  {
    v286 = *(_QWORD *)(v285 + 8);
    --*((_DWORD *)v4 + 70);
    v4[33] = v286;
    v287 = v4[7];
    *(_QWORD *)(v2 + 128) += v287;
    *(_QWORD *)(v2 + 120) = v287;
    v288 = sqlite3VdbeFrameRestore();
    v10 = 1;
    if ( *((_DWORD *)v6 + 2) == 4 )
      v288 = *(_DWORD *)(v4[17] + 24LL * v288 + 8) - 1;
    v5 = v4[17];
    v7 = v4[13];
    v825 = v5;
    v826 = v7;
    v6 = (unsigned __int8 *)(v5 + 24LL * v288);
    goto LABEL_61;
  }
  v812 = *((_DWORD *)v6 + 1);
  *((_DWORD *)v4 + 13) = v812;
  *((_BYTE *)v4 + 196) = v6[8];
  if ( v812 )
  {
    if ( *((_WORD *)v6 + 1) )
    {
      sqlite3VdbeError(v4, "%s constraint failed", off_1800CC890[*((unsigned __int16 *)v6 + 1)]);
      if ( *((_QWORD *)v6 + 2) )
        v4[21] = sqlite3MPrintf(v2, "%z: %s", v4[21]);
    }
    else
    {
      sqlite3VdbeError(v4, "%s", *((const char **)v6 + 2));
    }
    sqlite3_log(
      *((unsigned int *)v6 + 1),
      "abort at %d in [%s]: %s",
      -1431655765 * ((__int64)&v6[-v825] >> 3),
      (const char *)v4[31],
      (const char *)v4[21]);
  }
  v813 = sqlite3VdbeHalt(v4);
  v56 = v830;
  v14 = v813;
  if ( v813 == 5 )
    *((_DWORD *)v4 + 13) = 5;
  else
    v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
LABEL_1565:
  while ( 1 )
  {
    v816 = v842;
    if ( v843 < v842 )
      break;
    v817 = *(__int64 (__fastcall **)(__int64))(v56 + 528);
    if ( !v817 )
      break;
    v818 = *(_QWORD *)(v56 + 536);
    v842 += *(unsigned int *)(v56 + 544);
    v819 = v817(v818);
    v56 = v830;
    v3 = 0;
    if ( v819 )
    {
LABEL_1535:
      v842 = -1;
      goto LABEL_1536;
    }
  }
  *((_DWORD *)v4 + 57) += v843;
  if ( *((_DWORD *)v4 + 52) )
    sqlite3VdbeLeave(v4, v816, v56);
  return v14;
}

```

## disassembly

```asm
0x180092f80  mov     rax, rsp
0x180092f83  push    rbp
0x180092f84  push    rbx
0x180092f85  push    rsi
0x180092f86  push    rdi
0x180092f87  push    r12
0x180092f89  push    r13
0x180092f8b  push    r14
0x180092f8d  push    r15
0x180092f8f  lea     rbp, [rax-178h]
0x180092f96  sub     rsp, 238h
0x180092f9d  movaps  xmmword ptr [rax-58h], xmm6
0x180092fa1  movaps  xmmword ptr [rax-68h], xmm7
0x180092fa5  mov     rax, cs:__security_cookie
0x180092fac  xor     rax, rsp
0x180092faf  mov     [rbp+170h+var_70], rax
0x180092fb6  mov     r13, [rcx]
0x180092fb9  xor     r10d, r10d
0x180092fbc  mov     r15, rcx
0x180092fbf  mov     r8, [rcx+88h]
0x180092fc6  mov     r14, r8
0x180092fc9  mov     rsi, [rcx+68h]
0x180092fcd  mov     r9d, r10d
0x180092fd0  mov     [rsp+270h+var_210], rcx
0x180092fd5  mov     dil, [r13+64h]
0x180092fd9  mov     byte ptr [rsp+270h+var_230], dil
0x180092fde  mov     [rsp+270h+var_220], r8
0x180092fe3  mov     [rsp+270h+var_1F8], r13
0x180092fe8  mov     [rbp+170h+var_1E4], r10b
0x180092fec  mov     [rbp+170h+var_180], r10
0x180092ff0  mov     [rsp+270h+var_218], rsi
0x180092ff5  cmp     [rcx+0D0h], r10d
0x180092ffc  jz      short loc_18009300D
0x180092ffe  call    sqlite3VdbeEnter
0x180093003  mov     r9, [rbp+170h+var_180]
0x180093007  mov     r8, r14
0x18009300a  xor     r10d, r10d
0x18009300d  cmp     [r13+210h], r10
0x180093014  jz      short loc_180093032
0x180093016  mov     eax, [r15+0E4h]
0x18009301d  xor     edx, edx
0x18009301f  mov     ecx, [r13+220h]
0x180093026  div     ecx
0x180093028  sub     ecx, edx
0x18009302a  mov     eax, ecx
0x18009302c  mov     [rbp+170h+var_188], rax
0x180093030  jmp     short loc_18009303A
0x180093032  mov     [rbp+170h+var_188], 0FFFFFFFFFFFFFFFFh
0x18009303a  cmp     dword ptr [r15+34h], 7
0x18009303f  mov     r11d, 1
0x180093045  jz      loc_180099371
0x18009304b  mov     [r15+34h], r10d
0x18009304f  mov     [r15+48h], r10
0x180093053  mov     eax, [r13+198h]
0x18009305a  mov     [r13+298h], r10d
0x180093061  test    eax, eax
0x180093063  jnz     loc_180099329
0x180093069  movsxd  rax, dword ptr [r15+30h]
0x18009306d  mov     edx, r10d
0x180093070  mov     r12d, r10d
0x180093073  mov     dword ptr [rsp+270h+var_228], r10d
0x180093078  mov     [rsp+270h+var_22C], edx
0x18009307c  xorps   xmm7, xmm7
0x18009307f  mov     [rbp+170h+var_1A8], r10d
0x180093083  lea     rcx, [rax+rax*2]
0x180093087  lea     r14, [r8+rcx*8]
0x18009308b  lea     ecx, [r11+3]
0x18009308f  movzx   ebx, byte ptr [r14]
0x180093093  add     r9, r11
0x180093096  mov     [rbp+170h+var_1A0], r14
0x18009309a  mov     eax, 5
0x18009309f  mov     [rbp+170h+var_180], r9
0x1800930a3  cmp     ebx, 5Ch ; '\'
0x1800930a6  ja      loc_180095728
0x1800930ac  jz      loc_1800956D9
0x1800930b2  cmp     ebx, 2Dh ; '-'
0x1800930b5  ja      loc_18009473E
0x1800930bb  jz      loc_18009465D
0x1800930c1  cmp     ebx, 16h
0x1800930c4  ja      loc_180093F32
0x1800930ca  jz      loc_180093D15
0x1800930d0  cmp     ebx, 0Bh
0x1800930d3  ja      loc_180093AE8
0x1800930d9  jz      loc_180093ABD
0x1800930df  cmp     ebx, eax
0x1800930e1  ja      loc_1800938AD
0x1800930e7  jz      loc_18009386D
0x1800930ed  test    ebx, ebx
0x1800930ef  jz      loc_18009347F
0x1800930f5  sub     ebx, 1
0x1800930f8  jz      loc_180098F51
0x1800930fe  sub     ebx, 1
0x180093101  jz      loc_180093352
0x180093107  sub     ebx, 1
0x18009310a  jz      loc_1800932AA
0x180093110  cmp     ebx, 1
0x180093113  jnz     loc_180093298
0x180093119  mov     rdx, r14
0x18009311c  mov     rcx, r15
0x18009311f  call    out2Prerelease
0x180093124  movsxd  rcx, dword ptr [r14+4]
0x180093128  mov     r15, rax
0x18009312b  mov     rax, [r13+20h]
0x18009312f  mov     ebx, [r14+0Ch]
0x180093133  shl     rcx, 5
0x180093137  mov     r12, [rcx+rax+8]
0x18009313c  mov     rcx, r12
0x18009313f  call    sqlite3BtreePager
0x180093144  mov     rcx, rax
0x180093147  mov     rsi, rax
0x18009314a  call    sqlite3PagerGetJournalMode
0x18009314f  cmp     ebx, 0FFFFFFFFh
0x180093152  mov     rcx, rsi
0x180093155  mov     edi, eax
0x180093157  cmovz   ebx, eax
0x18009315a  call    sqlite3PagerOkToChangeJournalMode
0x18009315f  test    eax, eax
0x180093161  mov     edx, 1
0x180093166  mov     rcx, rsi
0x180093169  cmovz   ebx, edi
0x18009316c  call    sqlite3PagerFilename
0x180093171  mov     ecx, 5
0x180093176  cmp     ebx, ecx
0x180093178  jnz     short loc_1800931AC
0x18009317a  mov     rcx, rax
0x18009317d  call    sqlite3Strlen30
0x180093182  test    eax, eax
0x180093184  jz      short loc_180093192
0x180093186  mov     rcx, rsi
0x180093189  call    sqlite3PagerWalSupported
0x18009318e  test    eax, eax
0x180093190  jnz     short loc_1800931A7
0x180093192  mov     ebx, edi
0x180093194  mov     r12d, dword ptr [rsp+270h+var_228]
0x180093199  test    r12d, r12d
0x18009319c  jz      loc_180093232
0x1800931a2  jmp     loc_180093230
0x1800931a7  mov     ecx, 5
0x1800931ac  cmp     ebx, edi
0x1800931ae  jz      short loc_180093194
0x1800931b0  cmp     edi, ecx
0x1800931b2  jz      short loc_1800931B8
0x1800931b4  cmp     ebx, ecx
0x1800931b6  jnz     short loc_180093194
0x1800931b8  cmp     byte ptr [r13+65h], 0
0x1800931bd  jz      loc_180098E70
0x1800931c3  cmp     dword ptr [r13+0DCh], 1
0x1800931cb  jg      loc_180098E70
0x1800931d1  cmp     edi, ecx
0x1800931d3  jnz     short loc_1800931F4
0x1800931d5  mov     rdx, r13
0x1800931d8  mov     rcx, rsi
0x1800931db  call    sqlite3PagerCloseWal
0x1800931e0  mov     dword ptr [rsp+270h+var_228], eax
0x1800931e4  test    eax, eax
0x1800931e6  jnz     short loc_18009322B
0x1800931e8  mov     edx, ebx
0x1800931ea  mov     rcx, rsi
0x1800931ed  call    sqlite3PagerSetJournalMode
0x1800931f2  jmp     short loc_18009320B
0x1800931f4  cmp     edi, 4
0x1800931f7  jnz     short loc_180093204
0x1800931f9  lea     edx, [rdi-2]
0x1800931fc  mov     rcx, rsi
0x1800931ff  call    sqlite3PagerSetJournalMode
0x180093204  cmp     dword ptr [rsp+270h+var_228], 0
0x180093209  jnz     short loc_18009322B
0x18009320b  xor     edx, edx
0x18009320d  lea     ecx, [rdx+5]
0x180093210  cmp     ebx, ecx
0x180093212  mov     rcx, r12
0x180093215  setz    dl
0x180093218  inc     edx
0x18009321a  call    sqlite3BtreeSetVersion
0x18009321f  mov     r12d, eax
0x180093222  mov     dword ptr [rsp+270h+var_228], eax
0x180093226  jmp     loc_180093199
0x18009322b  mov     r12d, dword ptr [rsp+270h+var_228]
0x180093230  mov     ebx, edi
0x180093232  mov     edx, ebx
0x180093234  mov     rcx, rsi
0x180093237  call    sqlite3PagerSetJournalMode
0x18009323c  mov     ecx, eax
0x18009323e  mov     word ptr [r15+14h], 2202h
0x180093245  call    sqlite3JournalModename
0x18009324a  mov     rcx, rax
0x18009324d  mov     [r15+8], rax
0x180093251  call    sqlite3Strlen30
0x180093256  movzx   edi, byte ptr [rsp+270h+var_230]
0x18009325b  mov     rcx, r15
0x18009325e  mov     edx, edi
0x180093260  mov     [r15+10h], eax
0x180093264  mov     byte ptr [r15+16h], 1
0x180093269  call    sqlite3VdbeChangeEncoding
0x18009326e  mov     r15, [rsp+270h+var_210]
0x180093273  xor     r10d, r10d
0x180093276  test    r12d, r12d
0x180093279  jnz     loc_18009939D
0x18009327f  mov     rsi, [rsp+270h+var_218]
0x180093284  mov     r8, [rsp+270h+var_220]
0x180093289  mov     r11d, 1
0x18009328f  mov     edx, [rsp+270h+var_22C]
0x180093293  mov     ecx, 4
0x180093298  mov     r13, [rsp+270h+var_1F8]
0x18009329d  add     r14, 18h
0x1800932a1  mov     r9, [rbp+170h+var_180]
0x1800932a5  jmp     loc_18009308F
0x1800932aa  mov     r8d, [r14+8]
0x1800932ae  lea     rax, [rbp+170h+var_7C+4]
0x1800932b5  mov     edx, [r14+4]
0x1800932b9  lea     r9, [rbp+170h+var_7C]
0x1800932c0  mov     rcx, r13
0x1800932c3  mov     [rsp+270h+var_250], rax
0x1800932c8  mov     [rbp+170h+var_80], r10d
0x1800932cf  mov     [rbp+170h+var_7C], 0FFFFFFFFFFFFFFFFh
0x1800932da  call    sqlite3Checkpoint
0x1800932df  xor     r10d, r10d
0x1800932e2  mov     dword ptr [rsp+270h+var_228], eax
0x1800932e6  mov     r12d, eax
0x1800932e9  test    eax, eax
0x1800932eb  jz      short loc_18009330B
0x1800932ed  lea     ecx, [r10+5]
0x1800932f1  cmp     eax, ecx
0x1800932f3  jnz     loc_18009939D
0x1800932f9  mov     r12d, r10d
0x1800932fc  mov     dword ptr [rsp+270h+var_228], r10d
0x180093301  mov     [rbp+170h+var_80], 1
0x18009330b  movsxd  rax, dword ptr [r14+0Ch]
0x18009330f  mov     rdi, r10
0x180093312  imul    rbx, rax, 38h ; '8'
0x180093316  add     rbx, rsi
0x180093319  movsxd  rdx, [rbp+rdi*4+170h+var_80]
0x180093321  mov     rcx, rbx
0x180093324  call    sqlite3VdbeMemSetInt64
0x180093329  mov     r11d, 1
0x18009332f  add     rbx, 38h ; '8'
0x180093333  add     rdi, r11
0x180093336  cmp     rdi, 3
0x18009333a  jnz     short loc_180093319
0x18009333c  mov     dil, byte ptr [rsp+270h+var_230]
0x180093341  mov     r8, [rsp+270h+var_220]
0x180093346  mov     edx, [rsp+270h+var_22C]
0x18009334a  xor     r10d, r10d
0x18009334d  jmp     loc_180093293
0x180093352  mov     edx, [r14+8]
0x180093356  mov     dword ptr [rsp+270h+var_200], r10d
0x18009335b  test    edx, edx
0x18009335d  jz      short loc_180093376
0x18009335f  mov     rax, [r13+30h]
0x180093363  mov     rcx, 200100000h
0x18009336d  test    rcx, rax
0x180093370  jnz     loc_180098E9B
0x180093376  movsxd  rdi, dword ptr [r14+4]
0x18009337a  mov     rsi, [r13+20h]
0x18009337e  shl     rdi, 5
0x180093382  mov     rbx, [rdi+rsi+8]
0x180093387  test    rbx, rbx
0x18009338a  jz      loc_180093440
0x180093390  lea     r8, [rsp+270h+var_200]
0x180093395  mov     rcx, rbx
0x180093398  call    sqlite3BtreeBeginTrans
0x18009339d  xor     r10d, r10d
0x1800933a0  mov     dword ptr [rsp+270h+var_228], eax
0x1800933a4  mov     r12d, eax
0x1800933a7  test    eax, eax
0x1800933a9  jnz     loc_180098EB3
0x1800933af  test    byte ptr [r15+0C8h], 20h
0x1800933b7  jz      loc_180093449
0x1800933bd  cmp     [r14+8], r10d
0x1800933c1  jz      loc_180093449
0x1800933c7  cmp     [r13+65h], r10b
0x1800933cb  jz      short loc_1800933D7
0x1800933cd  cmp     dword ptr [r13+0DCh], 1
0x1800933d5  jle     short loc_180093449
0x1800933d7  mov     r8d, [r15+40h]
0x1800933db  test    r8d, r8d
0x1800933de  jnz     short loc_1800933F9
0x1800933e0  inc     dword ptr [r13+2F4h]
0x1800933e7  mov     r8d, [r13+2F0h]
0x1800933ee  add     r8d, [r13+2F4h]
0x1800933f5  mov     [r15+40h], r8d
0x1800933f9  dec     r8d
0x1800933fc  xor     edx, edx
0x1800933fe  mov     rcx, r13
0x180093401  call    sqlite3VtabSavepoint
0x180093406  xor     r10d, r10d
0x180093409  mov     dword ptr [rsp+270h+var_228], eax
0x18009340d  mov     r12d, eax
0x180093410  test    eax, eax
0x180093412  jnz     short loc_18009342A
0x180093414  mov     edx, [r15+40h]
0x180093418  mov     rcx, rbx
0x18009341b  call    sqlite3BtreeBeginStmt
0x180093420  mov     r12d, eax
0x180093423  mov     dword ptr [rsp+270h+var_228], eax
0x180093427  xor     r10d, r10d
0x18009342a  mov     rax, [r13+2F8h]
0x180093431  mov     [r15+58h], rax
0x180093435  mov     rax, [r13+300h]
0x18009343c  mov     [r15+60h], rax
  ... truncated ...
```
