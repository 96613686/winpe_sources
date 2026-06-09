# sqlite3VdbeExec

- ea: `0x1800ade30`
- end: `0x1800b43fe`
- name: `sqlite3VdbeExec`
- size: `26062`
- prototype: ``
- caller_count: `2`
- callee_count: `173`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180054cf8`
- `0x1800c6d20`

## callees

- `0x1800033d0`
- `0x180003fa0`
- `0x180003fb8`
- `0x180050e74`
- `0x1800523f0`
- `0x180052464`
- `0x180055354`
- `0x180055c34`
- `0x180061424`
- `0x180061750`
- `0x1800653f4`
- `0x18007399c`
- `0x1800740c0`
- `0x180082018`
- `0x18008378c`
- `0x1800854a4`
- `0x18008551c`
- `0x180085580`
- `0x1800855ac`
- `0x180085660`
- `0x180085678`
- `0x180085b60`
- `0x180085c58`
- `0x180085cc0`
- `0x180085d40`
- `0x180085d50`
- `0x180085d5c`
- `0x180085d68`
- `0x1800861bc`
- `0x180086224`
- `0x180086248`
- `0x180086258`
- `0x180086308`
- `0x1800863ec`
- `0x1800864f8`
- `0x18008695c`
- `0x180086e8c`
- `0x180086eac`
- `0x1800872c4`
- `0x1800872e4`
- `0x1800872f4`
- `0x180087314`
- `0x1800873cc`
- `0x180087430`
- `0x180087478`
- `0x180087b1c`
- `0x180087b5c`
- `0x180087b7c`
- `0x180087d4c`
- `0x180087da8`

## string_xrefs

- `0x1800b3f07`: `cannot open savepoint - SQL statements in progress`
- `0x1800b3e38`: `cannot commit transaction - SQL statements in progress`
- `0x1800b3ee9`: `cannot commit - no transaction is active`
- `0x1800b3ee2`: `cannot rollback - no transaction is active`

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
  __int64 v469; // rdx
  __int64 v470; // rax
  char v471; // cl
  __int64 v472; // rdx
  int v473; // ebx
  int v474; // ebx
  int v475; // ebx
  __int64 v476; // rax
  __int64 v477; // rdi
  __int64 v478; // rsi
  __int64 v479; // r15
  __int16 v480; // dx
  unsigned __int8 v481; // bl
  int v482; // ecx
  __int64 v483; // rdx
  __int64 v484; // r8
  int v485; // ecx
  int v486; // ecx
  int v487; // ecx
  __int128 v488; // rax
  __int64 v489; // rax
  int v490; // eax
  __int16 v491; // ax
  double v492; // xmm6_8
  __int64 v493; // rdx
  double v494; // xmm0_8
  __int64 v495; // rbx
  __int64 v496; // rdx
  __int64 v497; // rax
  double v498; // xmm0_8
  __int16 v499; // ax
  __int64 v500; // r13
  __int16 v501; // r12
  __int64 v502; // rdi
  __int64 v503; // rbx
  int v504; // eax
  __int16 v505; // si
  int v506; // eax
  unsigned __int64 v507; // r15
  int v508; // ebx
  int v509; // ebx
  int v510; // ebx
  __int64 v511; // rbx
  __int64 Cursor; // rax
  int v513; // ecx
  __int64 v514; // rdi
  __int64 v515; // rbx
  int v516; // r12d
  __int64 v517; // rcx
  __int64 v518; // r15
  __int64 v519; // rax
  __int64 v520; // r13
  int v521; // esi
  unsigned __int8 v522; // cl
  unsigned __int8 v523; // al
  __int64 v524; // rbx
  __int64 v525; // r8
  __int64 v526; // rax
  __int64 v527; // rcx
  unsigned int v528; // eax
  int v529; // ebx
  int v530; // ebx
  int v531; // ebx
  int v532; // ebx
  __int64 v533; // rax
  __int64 v534; // rdx
  __int64 v535; // rcx
  __int64 v536; // rax
  __int64 v537; // rdx
  __int64 v538; // rsi
  __int64 v539; // rdx
  __int64 v540; // rcx
  unsigned int v541; // eax
  __int64 v542; // rax
  _QWORD *v543; // r15
  unsigned int v544; // eax
  unsigned int v545; // eax
  __int64 v546; // r13
  _DWORD *v547; // r12
  __int64 v548; // rdi
  unsigned int v549; // ebx
  __int64 v550; // rax
  __int64 v551; // rcx
  __int64 v552; // rax
  __int64 v553; // r9
  __int64 v554; // rdx
  __int64 v555; // rbx
  int v556; // ecx
  __int64 v557; // rcx
  __int64 v558; // rax
  int v559; // ebx
  int v560; // ebx
  int v561; // ebx
  int v562; // ebx
  __int64 v563; // rcx
  __int64 v564; // rdx
  __int64 v565; // rax
  __int64 v566; // rbx
  __int64 v567; // r8
  __int64 v568; // rdi
  __int64 v569; // rsi
  __int16 v570; // r8
  __int64 v571; // r9
  unsigned int v572; // eax
  __int64 v573; // rcx
  void (__fastcall *v574)(_QWORD, __int64, __int64, _QWORD, __int64, int); // rax
  __int64 v575; // rdx
  __int64 *v576; // rsi
  __int64 v577; // rdi
  unsigned int v578; // eax
  __int64 v579; // rax
  __int64 v580; // rcx
  __int64 *v581; // rbx
  __int64 v582; // rax
  int v583; // ebx
  unsigned int v584; // eax
  _QWORD *v585; // rax
  __int64 v586; // rdx
  __int64 v587; // rdx
  int v588; // eax
  __int64 v589; // rcx
  __int64 v590; // rax
  __int64 v591; // rbx
  int v592; // edi
  __int64 v593; // rax
  unsigned int v594; // eax
  bool v595; // sf
  __int64 v596; // rcx
  unsigned int v597; // eax
  __int64 v598; // r8
  int v599; // ebx
  int v600; // ebx
  int v601; // ebx
  int v602; // ebx
  __int64 v603; // rbx
  __int64 v604; // rdi
  unsigned int v605; // eax
  unsigned int v606; // eax
  int Writeable; // eax
  unsigned int v608; // eax
  __int64 v609; // rcx
  __int64 v610; // r8
  __int64 v611; // rdx
  __int64 v612; // rax
  unsigned int v613; // eax
  int v614; // r15d
  __int64 v615; // rbx
  unsigned int v616; // eax
  __int64 v617; // rax
  __int64 v618; // rdx
  __int64 v619; // rcx
  __int64 v620; // rdi
  __int64 v621; // rbx
  __int64 v622; // rax
  __int64 *v623; // rcx
  __int64 v624; // rbx
  unsigned int v625; // eax
  __int64 v626; // rdi
  __int64 v627; // rbx
  unsigned int v628; // eax
  unsigned int v629; // eax
  __int64 v630; // rax
  __int64 v631; // rcx
  __int64 v632; // rdi
  __int64 v633; // rbx
  unsigned int v634; // eax
  __int16 v635; // r8
  __int64 v636; // rcx
  __int64 v637; // r9
  __int64 v638; // rcx
  __int64 v639; // rax
  __int64 v640; // rdi
  __int64 v641; // rsi
  __int64 v642; // rcx
  int IsValidNN; // eax
  unsigned int v644; // eax
  __int64 v645; // rdx
  __int64 v646; // rbx
  __int64 valid; // rax
  __int64 v648; // rcx
  __int64 v649; // rax
  _QWORD *v650; // rbx
  __int64 v651; // rdi
  __int64 v652; // rax
  unsigned int v653; // eax
  __int64 v654; // rdx
  unsigned int v655; // eax
  int v656; // eax
  int v657; // ebx
  int v658; // ebx
  int v659; // ebx
  int v660; // ebx
  __int64 v661; // rcx
  __int64 v662; // rdx
  __int64 v663; // rax
  unsigned int v664; // eax
  __int64 v665; // rdx
  __int64 v666; // rbx
  unsigned int v667; // edi
  __int64 v668; // rcx
  __int64 v669; // rdx
  __int64 v670; // rcx
  __int64 v671; // rcx
  __int64 v672; // rax
  __int64 v673; // rbx
  unsigned int v674; // eax
  unsigned int v675; // eax
  __int64 v676; // rdx
  __int64 v677; // rcx
  __int64 v678; // r8
  int v679; // ebx
  int v680; // ebx
  int v681; // ebx
  int v682; // ebx
  __int64 v683; // rbx
  __int64 v684; // rcx
  unsigned int inited; // eax
  __int64 v686; // rbx
  int v687; // eax
  __int64 v688; // r8
  __int64 v689; // rbx
  __int64 v690; // rbx
  char v691; // di
  int v692; // esi
  unsigned int v693; // eax
  const char *v694; // r8
  __int64 v695; // rax
  __int64 v696; // rcx
  _QWORD *v697; // rbx
  __int64 v698; // r8
  __int64 v699; // r9
  unsigned int v700; // eax
  int v701; // ebx
  int v702; // ebx
  int v703; // ebx
  int v704; // ebx
  __int64 v705; // rax
  __int64 v706; // rdi
  __int64 v707; // rbx
  __int64 v708; // rdx
  __int64 v709; // r8
  __int64 v710; // rdi
  int v711; // eax
  __int64 v712; // rdx
  int v713; // r9d
  __int64 v714; // rbx
  __int64 v715; // r9
  unsigned __int64 v716; // rsi
  __int64 (__fastcall *v717)(_QWORD); // rax
  __int64 v718; // rbx
  int v719; // eax
  __int64 v720; // rcx
  int v721; // ebx
  int v722; // ebx
  __int64 v723; // rdi
  __int64 v724; // rbx
  __int64 v725; // rcx
  _DWORD *v726; // rbx
  __int64 v727; // r8
  int v728; // edx
  __int64 v729; // rsi
  __int64 v730; // rbx
  __int64 v731; // rdx
  __int64 v732; // rdx
  int v733; // eax
  __int64 v734; // rcx
  _QWORD *v735; // rdi
  _QWORD *v736; // rbx
  _DWORD *v737; // r8
  __int64 v738; // rax
  __int64 v739; // rdx
  int v740; // eax
  const char *v741; // rax
  int v742; // ebx
  int v743; // ebx
  int v744; // ebx
  int v745; // ebx
  __int64 v746; // rbx
  unsigned int v747; // eax
  int v748; // ebx
  int v749; // ebx
  int v750; // ebx
  __int64 v751; // rax
  __int64 *v752; // rbx
  __int64 v753; // rdi
  __int64 v754; // r9
  __int64 v755; // rax
  __int64 v756; // rax
  __int64 v757; // rax
  __int64 v758; // rbx
  unsigned int v759; // eax
  __int64 v760; // rax
  __int64 v761; // r15
  _QWORD *v762; // rsi
  __int64 v763; // rcx
  __int64 *v764; // rdi
  __int64 v765; // rbx
  __int64 v766; // r9
  int v767; // ebx
  int v768; // ebx
  int v769; // ebx
  int v770; // ebx
  _QWORD *v771; // rdi
  __int64 v772; // rdx
  __int64 v773; // rbx
  unsigned int Page; // eax
  _QWORD *v775; // rbx
  int v776; // esi
  __int64 v777; // rbx
  __int64 v778; // rdi
  unsigned int v779; // eax
  __int64 v780; // rdi
  __int64 v781; // rax
  __int64 v782; // rbx
  __int64 *v783; // rsi
  __int64 v784; // r15
  __int16 v785; // ax
  unsigned int v786; // eax
  const char *v787; // rax
  __int64 v788; // rdi
  _QWORD *v789; // rax
  _QWORD *v790; // rbx
  __int64 v791; // rax
  int v792; // ebx
  int v793; // ebx
  int v794; // ebx
  char v795; // al
  const char *v796; // r9
  __int64 v797; // rbx
  __int64 v798; // rbx
  int v799; // eax
  int ii; // ecx
  __int64 v801; // rax
  __int64 v802; // rbx
  unsigned __int64 v803; // rax
  unsigned __int64 v804; // r8
  __int64 v805; // rdx
  __int64 v806; // rcx
  __int64 v807; // rdx
  const char *v808; // r8
  const char *v809; // rdx
  int v810; // ebx
  int v811; // ecx
  char v812; // al
  const char *v813; // rdx
  unsigned int v814; // eax
  int v815; // ecx
  unsigned int v816; // eax
  __int64 v817; // rbx
  const char *v818; // rax
  unsigned __int64 v819; // rdx
  __int64 (__fastcall *v820)(__int64); // rax
  __int64 v821; // rcx
  int v822; // eax
  int v824; // [rsp+30h] [rbp-D8h]
  unsigned __int8 v825; // [rsp+48h] [rbp-C0h]
  unsigned int v826; // [rsp+4Ch] [rbp-BCh]
  unsigned int Table; // [rsp+50h] [rbp-B8h]
  __int64 v828; // [rsp+58h] [rbp-B0h]
  __int64 v829; // [rsp+60h] [rbp-A8h]
  unsigned int *v831; // [rsp+70h] [rbp-98h] BYREF
  __int64 v832; // [rsp+78h] [rbp-90h] BYREF
  __int64 v833; // [rsp+80h] [rbp-88h]
  int *v834; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v835; // [rsp+90h] [rbp-78h] BYREF
  char v836; // [rsp+94h] [rbp-74h]
  unsigned int v837; // [rsp+98h] [rbp-70h]
  __int128 v838; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v839; // [rsp+B0h] [rbp-58h]
  __int128 v840; // [rsp+C0h] [rbp-48h]
  int v841; // [rsp+D0h] [rbp-38h]
  __int64 v842; // [rsp+D8h] [rbp-30h] BYREF
  int v843; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v844; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v845; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v846; // [rsp+F8h] [rbp-10h]
  __int128 v847; // [rsp+100h] [rbp-8h] BYREF
  __int128 v848; // [rsp+110h] [rbp+8h]
  __int128 v849; // [rsp+120h] [rbp+18h]
  __int64 v850; // [rsp+130h] [rbp+28h]
  __int128 v851; // [rsp+138h] [rbp+30h] BYREF
  __int128 v852; // [rsp+148h] [rbp+40h]
  __int128 v853; // [rsp+158h] [rbp+50h]
  __int64 v854; // [rsp+168h] [rbp+60h]
  _OWORD v855[2]; // [rsp+170h] [rbp+68h] BYREF
  __int128 v856; // [rsp+190h] [rbp+88h]
  __int64 v857; // [rsp+1A0h] [rbp+98h]
  char v858; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v859; // [rsp+1A9h] [rbp+A1h]
  char v860; // [rsp+1ABh] [rbp+A3h]
  int v861; // [rsp+1ACh] [rbp+A4h]
  int v862; // [rsp+1F8h] [rbp+F0h]
  __int64 v863; // [rsp+1FCh] [rbp+F4h] BYREF

  v2 = *a1;
  v3 = 0;
  v4 = a1;
  v5 = a1[17];
  v6 = (unsigned __int8 *)v5;
  v7 = a1[13];
  v8 = 0;
  v9 = *(_BYTE *)(*a1 + 100);
  v825 = v9;
  v828 = v5;
  v833 = *a1;
  v836 = 0;
  v846 = 0;
  v829 = v7;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter(a1, a2, v5, 0);
    v8 = v846;
    v5 = (__int64)v6;
    v3 = 0;
  }
  if ( *(_QWORD *)(v2 + 528) )
    v845 = (unsigned int)(*(_DWORD *)(v2 + 544) - *((_DWORD *)v4 + 57) % *(_DWORD *)(v2 + 544));
  else
    v845 = -1;
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
  v826 = 0;
  v841 = 0;
  v6 = (unsigned __int8 *)(v5 + 24 * v12);
LABEL_9:
  v15 = *v6;
  v16 = v10 + v8;
  v842 = (__int64)v6;
  v846 = v16;
  if ( (unsigned int)v15 > 0x5C )
  {
    if ( (unsigned int)v15 <= 0x8C )
    {
      if ( (_DWORD)v15 == 140 )
      {
        v648 = *((int *)v6 + 1);
        LODWORD(v832) = 0;
        *(_QWORD *)&v840 = 0;
        v649 = v4[15];
        v838 = 0;
        v839 = 0;
        v650 = *(_QWORD **)(v649 + 8 * v648);
        v651 = v650[6];
        *(_QWORD *)&v838 = v650[7];
        WORD6(v839) = *((_WORD *)v6 + 6);
        v652 = *((int *)v6 + 2);
        BYTE14(v839) = 0;
        *((_QWORD *)&v838 + 1) = v7 + 56 * v652;
        v653 = sqlite3BtreeIndexMoveto(v651, &v838, &v832);
        v3 = 0;
        Table = v653;
        v14 = v653;
        if ( v653 )
          goto LABEL_1546;
        if ( (_DWORD)v832 )
        {
          if ( *((_WORD *)v6 + 1) )
          {
            v656 = sqlite3WritableSchema(v2);
            v3 = 0;
            if ( !v656 )
            {
              v814 = sqlite3ReportError(779, 99938, "index corruption");
              goto LABEL_1530;
            }
          }
        }
        else
        {
          LOBYTE(v654) = 4;
          v655 = sqlite3BtreeDelete(v651, v654);
          v3 = 0;
          Table = v655;
          v14 = v655;
          if ( v655 )
            goto LABEL_1546;
        }
        v650[4] = 0;
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
                LODWORD(v832) = 0;
                sqlite3BtreeGetMeta(*(_QWORD *)(v455 + v453 + 8), v454, &v832);
                v283 = (unsigned int **)out2Prerelease(v4, v6);
                v284 = (unsigned int *)(int)v832;
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
                      LOBYTE(v5) = v825;
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
                    v831 = 0;
                    v347 = *(_QWORD *)(v346 + 8 * v345);
                    if ( *((_DWORD *)v6 + 3) )
                    {
                      v831 = (unsigned int *)sqlite3BtreeRowCountEst(*(_QWORD *)(v347 + 48));
                    }
                    else
                    {
                      v348 = sqlite3BtreeCount(v2, *(_QWORD *)(v347 + 48), &v831);
                      v3 = 0;
                      Table = v348;
                      v14 = v348;
                      if ( v348 )
                        goto LABEL_1546;
                    }
                    v349 = (unsigned int **)out2Prerelease(v4, v6);
                    *v349 = v831;
                    goto LABEL_1308;
                  }
                  v350 = 0;
                  v351 = (char *)*((_QWORD *)v6 + 2);
                  v352 = 0;
                  v353 = *((_DWORD *)v6 + 3);
                  v354 = 0;
                  v355 = *((_DWORD *)v6 + 2);
                  v356 = (int *)(v7 + 56LL * *((int *)v6 + 1));
                  LODWORD(v832) = 0;
                  v831 = 0;
                  v834 = v356;
                  v357 = &v356[14 * (v355 - (int)v10)];
                  v842 = (__int64)v357;
                  if ( v351 )
                  {
                    v358 = *v351;
                    v359 = v356;
                    do
                    {
                      LOBYTE(v5) = v825;
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
                    v354 = v832;
                    v350 = v831;
                    v357 = (int *)v842;
                  }
                  v361 = v834;
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
                          v831 = (unsigned int *)((char *)v350 + v372);
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
                    v361 = v834;
LABEL_697:
                    if ( j == v361 )
                    {
                      v376 = v829 + 56LL * v353;
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
                      v382 = v831;
                      if ( (__int64)v831 + v381 <= *(int *)(v376 + 32) )
                      {
                        *(_QWORD *)(v376 + 8) = *(_QWORD *)(v376 + 40);
                        goto LABEL_712;
                      }
                      v2 = v833;
                      if ( (__int64)v831 + v381 <= *(int *)(v833 + 136) )
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
                        v387 = v834;
                        v388 = v842;
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
                              v391 = *((unsigned __int8 *)qword_18013D650 + v389);
                              v392 = *((unsigned __int8 *)qword_18013D650 + v389) - 1;
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
                    v350 = v831;
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
                      v5 = v828;
                      goto LABEL_976;
                    }
                  }
                  LOBYTE(v5) = v825;
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
                          off_18010BBA8[*((unsigned __int8 *)qword_1801400C0 + (v13 & 0x3F))],
                          off_180158610[(unsigned int)(v5 - 1)],
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
                v7 = v829;
                goto LABEL_978;
              }
              v835 = 0;
              v851 = 0;
              v854 = 0;
              v413 = v4[15];
              v852 = 0;
              v853 = 0;
              v414 = *((_DWORD *)v6 + 2);
              v415 = *(_QWORD *)(v413 + 8LL * *((int *)v6 + 1));
LABEL_776:
              LODWORD(v834) = v414;
              while ( 1 )
              {
                v416 = *(unsigned int **)(v415 + 88);
                v417 = *((_DWORD *)v4 + 11);
                v831 = v416;
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
                      v835 = *(_DWORD *)(v415 + 4LL * v414 + 120);
                      goto LABEL_849;
                    }
                    v427 = (int *)(v415 + 64);
                    if ( *(_DWORD *)(v415 + 64) >= *v416 )
                    {
                      v443 = 0;
                      v835 = 0;
                      goto LABEL_841;
                    }
                    v431 = *(_QWORD *)(v415 + 96);
                    v832 = v431;
                    if ( !v431 )
                    {
                      v851 = 0;
                      v852 = 0;
                      v854 = 0;
                      v853 = 0;
                      v434 = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v415 + 48), *v416, &v851);
                      v3 = 0;
                      Table = v434;
                      v14 = v434;
                      if ( v434 )
                        goto LABEL_1546;
                      v431 = *((_QWORD *)&v851 + 1);
LABEL_811:
                      v832 = v431;
                    }
                    v435 = *v430;
                    v10 = 1;
                    v436 = (unsigned int)v834;
                    v437 = (unsigned __int8 *)(v431 + (unsigned int)*v427);
                    v438 = v416[v435];
                    v439 = v431 + *v416;
                    v440 = v831;
                    do
                    {
                      v835 = *v437;
                      *(_DWORD *)(v415 + 4LL * (int)v435 + 120) = v835;
                      if ( v835 >= 0x80 )
                      {
                        v437 += (unsigned __int8)sqlite3GetVarint32(v437, &v835);
                        *(_DWORD *)(v415 + 4LL * (int)v435 + 120) = v835;
                        if ( v835 < 0x80 )
                          v441 = *((unsigned __int8 *)qword_18013D650 + v835);
                        else
                          v441 = (v835 - 12) >> 1;
                        v440 = v831;
                        v10 = 1;
                      }
                      else
                      {
                        ++v437;
                        v441 = *((unsigned __int8 *)qword_18013D650 + (unsigned __int8)v835);
                      }
                      v438 += v441;
                      LODWORD(v435) = v435 + 1;
                      v440[(int)v435] = v438;
                    }
                    while ( (unsigned int)v435 <= v436 && (unsigned __int64)v437 < v439 );
                    v6 = (unsigned __int8 *)v842;
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
                      v442 = (_DWORD)v437 - v832;
                      *(_WORD *)(v415 + 74) = v435;
                      *(_DWORD *)(v415 + 64) = v442;
                      if ( !*(_QWORD *)(v415 + 96) && ((WORD2(v852) & 0x9000) != 0 || (_DWORD)v853) )
                      {
                        vdbeMemClear(&v851);
                        v443 = v835;
                        v3 = 0;
                        v416 = v831;
                        v414 = (unsigned int)v834;
                        v10 = 1;
                      }
                      else
                      {
                        v443 = v835;
                        v416 = v831;
                        v414 = (unsigned int)v834;
                      }
LABEL_841:
                      if ( *(unsigned __int16 *)(v415 + 74) <= v414 )
                      {
                        v7 = v829;
                        v445 = v829 + 56LL * *((int *)v6 + 3);
                        if ( v6[1] == 0xF6 )
                        {
                          sqlite3VdbeMemShallowCopy(v829 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2), 0x2000);
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
                          vdbeMemClearExternAndSetNull(v829 + 56LL * *((int *)v6 + 3));
                        }
LABEL_844:
                        v14 = Table;
                        v4 = a1;
LABEL_422:
                        v9 = v825;
                        goto LABEL_244;
                      }
LABEL_849:
                      v7 = v829;
                      v446 = v829 + 56LL * *((int *)v6 + 3);
                      if ( (*(_WORD *)(v446 + 20) & 0x9000) != 0 )
                      {
                        vdbeMemClearExternAndSetNull(v829 + 56LL * *((int *)v6 + 3));
                        v443 = v835;
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
                        *(_BYTE *)(v446 + 22) = v825;
                        v449 = (unsigned int)(v448 + 2);
                        if ( *(_DWORD *)(v446 + 32) >= (int)v449 )
                        {
                          *(_QWORD *)(v446 + 8) = *(_QWORD *)(v446 + 40);
                        }
                        else
                        {
                          v2 = v833;
                          if ( (int)v448 > *(_DWORD *)(v833 + 136) )
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
                        *(_WORD *)(v446 + 20) = word_18013EDD0[v835 & 1];
                        goto LABEL_145;
                      }
                      *(_BYTE *)(v446 + 22) = v825;
                      v450 = v6[2] & 0xC0;
                      if ( v450 && (v450 == (char)0x80 || v835 >= 0xC && ((v835 & 1) == 0 || v450 == -64))
                        || (v835 < 0x80
                          ? (v451 = *((unsigned __int8 *)qword_18013D650 + v835))
                          : (v451 = (v835 - 12) >> 1),
                            !v451) )
                      {
                        sqlite3VdbeSerialGet(&qword_18013D1A0, v835, v446);
                        goto LABEL_844;
                      }
                      v4 = a1;
                      v452 = vdbeColumnFromOverflow(v415, v414, v835, v416[v414], *((_DWORD *)a1 + 11), v841, v446);
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
                      v9 = v825;
LABEL_52:
                      v5 = v828;
                      v10 = 1;
                      v13 = v826;
                      goto LABEL_53;
                    }
                    if ( !*(_QWORD *)(v415 + 96) && ((WORD2(v852) & 0x9000) != 0 || (_DWORD)v853) )
                    {
                      vdbeMemClear(&v851);
                      v3 = 0;
                      v10 = 1;
                    }
LABEL_836:
                    v5 = v828;
                    v444 = *(_DWORD *)(v828 + 12);
                    if ( v444 > 0 )
                    {
                      v14 = Table;
                      v4 = a1;
                      v6 = (unsigned __int8 *)(v828 + 24LL * (v444 - 1));
LABEL_838:
                      v7 = v829;
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
              v468 = sqlite3VdbeIntValue(v460, v460);
              v470 = sqlite3VdbeIntValue(v459, v469);
              v471 = *v6;
              v472 = v470;
              if ( *v6 == 102 )
              {
                v468 &= v470;
LABEL_900:
                v3 = 0;
LABEL_915:
                *(_QWORD *)v461 = v468;
                *(_WORD *)(v461 + 20) &= 0xF244u;
                *(_WORD *)(v461 + 20) |= 4u;
LABEL_949:
                v7 = v829;
LABEL_950:
                v9 = v825;
                goto LABEL_951;
              }
              if ( v471 == 103 )
              {
                v468 |= v470;
                goto LABEL_900;
              }
              v3 = 0;
              if ( !v470 )
                goto LABEL_915;
              if ( v470 < 0 )
              {
                v471 = -47 - v471;
                if ( v470 <= -64 )
                  goto LABEL_906;
                v472 = -v470;
              }
              if ( v472 < 64 )
              {
                if ( v471 == 104 )
                {
                  v468 <<= v472;
                }
                else if ( v468 >= 0 )
                {
                  v468 = (unsigned __int64)v468 >> v472;
                }
                else
                {
                  v468 = ((unsigned __int64)v468 >> v472) | (-1LL << (64 - (unsigned __int8)v472));
                }
                goto LABEL_915;
              }
LABEL_906:
              if ( v468 >= 0 || v471 == 104 )
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
            v508 = v15 - 112;
            if ( v508 )
            {
              v509 = v508 - 1;
              if ( v509 )
              {
                v510 = v509 - 1;
                if ( !v510 )
                {
                  v514 = v7 + 56LL * *((int *)v6 + 1);
                  v515 = v7 + 56LL * *((int *)v6 + 2);
                  if ( (*(_WORD *)(v515 + 20) & 0x9000) != 0 )
                  {
                    vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 2));
                    v13 = v826;
                    v3 = 0;
                    v10 = 1;
                  }
                  else
                  {
                    *(_WORD *)(v515 + 20) = v10;
                  }
                  if ( ((unsigned __int8)v10 & *(_BYTE *)(v514 + 20)) == 0 )
                  {
                    *(_WORD *)(v515 + 20) = 4;
                    *(_QWORD *)v515 = ~sqlite3VdbeIntValue(v514, v13);
                    goto LABEL_422;
                  }
                  goto LABEL_623;
                }
                if ( v510 != 1 )
                  goto LABEL_53;
                v511 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2));
                Cursor = allocateCursor(v4, *((unsigned int *)v6 + 1), (unsigned int)*(__int16 *)(v511 + 72), 0);
                if ( Cursor )
                {
                  *(_DWORD *)(Cursor + 8) |= 1u;
                  *(_BYTE *)(Cursor + 2) = 1;
                  *(_QWORD *)(Cursor + 56) = *(_QWORD *)(v511 + 56);
                  *(_BYTE *)(Cursor + 4) = *(_BYTE *)(v511 + 4);
                  *(_DWORD *)(Cursor + 68) = *(_DWORD *)(v511 + 68);
                  v513 = *(_DWORD *)(Cursor + 8) ^ (*(_DWORD *)(v511 + 8) ^ *(_DWORD *)(Cursor + 8)) & 4;
                  *(_DWORD *)(Cursor + 8) = v513;
                  *(_QWORD *)(Cursor + 16) = *(_QWORD *)(v511 + 16);
                  *(_DWORD *)(Cursor + 8) = v513 | 8;
                  *(_DWORD *)(v511 + 8) |= 8u;
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
            v516 = *((_DWORD *)v6 + 3);
            v517 = *(_QWORD *)(v2 + 32);
            v518 = *((unsigned int *)v6 + 2);
            v519 = 32LL * v516;
            v520 = *(_QWORD *)(v519 + v517 + 8);
            if ( *v6 == 113 )
            {
              v521 = *((_WORD *)v6 + 1) & 8 | 4;
              v522 = *(_BYTE *)(*(_QWORD *)(v519 + v517 + 24) + 112LL);
              if ( v522 < *((_BYTE *)a1 + 197) )
                *((_BYTE *)a1 + 197) = v522;
            }
            else
            {
              v521 = 0;
            }
            if ( (v6[2] & 0x10) != 0 )
            {
              sqlite3VdbeMemIntegerify(v829 + 56 * v518);
              LODWORD(v518) = *(_DWORD *)(v829 + 56 * v518);
            }
            v523 = v6[1];
            if ( v523 == 0xF8 )
            {
              v524 = *((_QWORD *)v6 + 2);
              v525 = *(unsigned __int16 *)(v524 + 8);
            }
            else
            {
              v525 = 0;
              v524 = 0;
              if ( v523 == 0xFD )
                v525 = *((unsigned int *)v6 + 4);
            }
            v526 = allocateCursor(a1, *((unsigned int *)v6 + 1), v525, 0);
            v462 = v526;
            if ( v526 )
            {
              v527 = *(_QWORD *)(v526 + 48);
              *(_DWORD *)(v526 + 8) |= 4u;
              *(_BYTE *)(v526 + 1) = v516;
              *(_BYTE *)(v526 + 2) = 1;
              *(_DWORD *)(v526 + 68) = v518;
              v528 = sqlite3BtreeCursor(v520, v518, v521, v524, v527);
              v4 = a1;
              v14 = v528;
              v7 = v829;
              *(_QWORD *)(v462 + 56) = v524;
              Table = v528;
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
            v473 = v15 - 106;
            if ( v473 )
            {
              v474 = v473 - 1;
              if ( v474 )
              {
                v475 = v474 - 1;
                if ( v475 )
                {
                  if ( (unsigned int)(v475 - 1) > 1 )
                    goto LABEL_53;
                }
              }
            }
            v476 = *((int *)v6 + 3);
            v477 = v7 + 56LL * *((int *)v6 + 1);
            v478 = 56LL * *((int *)v6 + 2) + v7;
            v844 = 0;
            v479 = v829 + 56 * v476;
            v480 = *(_WORD *)(v478 + 20);
            if ( (*(_BYTE *)(v477 + 20) & (unsigned __int8)v480 & 4) == 0 )
            {
              if ( ((unsigned __int8)(*(_BYTE *)(v477 + 20) | v480) & (unsigned __int8)v10) != 0 )
              {
LABEL_973:
                if ( (*(_WORD *)(v479 + 20) & 0x9000) == 0 )
                {
                  v10 = 1;
                  *(_WORD *)(v479 + 20) = 1;
LABEL_976:
                  v13 = v826;
                  goto LABEL_977;
                }
                vdbeMemClearExternAndSetNull(v479);
LABEL_854:
                v4 = a1;
                goto LABEL_421;
              }
              v481 = numericType(v477);
              if ( (v481 & (unsigned __int8)numericType(v478) & 4) == 0 )
                goto LABEL_955;
              v3 = 0;
              v10 = 1;
            }
            v482 = *v6;
            v483 = *(_QWORD *)v478;
            v484 = *(_QWORD *)v477;
            v844 = *(_QWORD *)v478;
            v485 = v482 - 106;
            if ( !v485 )
            {
              if ( v484 < 0 )
              {
                if ( v483 < 0 && (__int64)(0x8000000000000001uLL - v483) > v484 + 1 )
                  goto LABEL_955;
              }
              else if ( v483 > 0 && 0x7FFFFFFFFFFFFFFFLL - v483 < v484 )
              {
                goto LABEL_955;
              }
              v489 = v483 + v484;
              goto LABEL_946;
            }
            v486 = v485 - 1;
            if ( v486 )
            {
              v487 = v486 - 1;
              if ( v487 )
              {
                if ( v487 != 1 )
                {
                  if ( v484 )
                  {
                    v488 = v483;
                    if ( v484 == -1 )
                      v484 = v10;
                    v844 = v488 % v484;
                    goto LABEL_947;
                  }
                  goto LABEL_972;
                }
                if ( !v484 )
                  goto LABEL_972;
                if ( v484 != -1 || v483 != 0x8000000000000000uLL )
                {
                  v489 = v483 / v484;
LABEL_946:
                  v844 = v489;
LABEL_947:
                  *(_QWORD *)v479 = v844;
                  v491 = *(_WORD *)(v479 + 20) & 0xF240 | 4;
LABEL_948:
                  *(_WORD *)(v479 + 20) = v491;
                  v4 = a1;
                  goto LABEL_949;
                }
LABEL_955:
                v492 = sqlite3VdbeRealValue(v477);
                v494 = sqlite3VdbeRealValue(v478);
                switch ( *v6 )
                {
                  case 'j':
                    v498 = v494 + v492;
                    break;
                  case 'k':
                    v498 = v494 - v492;
                    break;
                  case 'l':
                    v498 = v494 * v492;
                    break;
                  case 'm':
                    if ( v492 == 0.0 )
                    {
                      v3 = 0;
                      goto LABEL_972;
                    }
                    v498 = v494 / v492;
                    break;
                  default:
                    v495 = sqlite3VdbeIntValue(v477, v493);
                    v497 = sqlite3VdbeIntValue(v478, v496);
                    v3 = 0;
                    v844 = v497;
                    if ( v495 )
                    {
                      if ( v495 == -1 )
                        v495 = 1;
                      v498 = (double)(int)(v497 % v495);
LABEL_969:
                      if ( (*(_QWORD *)&v498 & 0xFFFFFFFFFFFFFLL) == 0
                        || (*(_QWORD *)&v498 & 0x7FF0000000000000LL) != 0x7FF0000000000000LL )
                      {
                        v499 = *(_WORD *)(v479 + 20);
                        *(double *)v479 = v498;
                        v491 = v499 & 0xF240 | 8;
                        goto LABEL_948;
                      }
                    }
LABEL_972:
                    v5 = v828;
                    goto LABEL_973;
                }
                v3 = 0;
                goto LABEL_969;
              }
              v490 = sqlite3MulInt64(&v844, v484);
            }
            else
            {
              v490 = sqlite3SubInt64(&v844, v484);
            }
            v3 = 0;
            if ( !v490 )
              goto LABEL_947;
            goto LABEL_955;
          }
          v500 = v7 + 56LL * *((int *)v6 + 1);
          v501 = *(_WORD *)(v500 + 20);
          v502 = v7 + 56LL * *((int *)v6 + 2);
          v503 = v7 + 56LL * *((int *)v6 + 3);
          if ( ((unsigned __int8)(*(_BYTE *)(v502 + 20) | v501) & (unsigned __int8)v10) != 0 )
          {
            if ( (*(_WORD *)(v503 + 20) & 0x9000) == 0 )
            {
              v14 = Table;
              *(_WORD *)(v503 + 20) = v10;
              goto LABEL_148;
            }
            v433 = v7 + 56LL * *((int *)v6 + 3);
            goto LABEL_803;
          }
          if ( (v501 & 0x12) != 0 )
          {
            if ( (v501 & 0x400) == 0 )
              goto LABEL_989;
            v504 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 1));
          }
          else
          {
            LOBYTE(v13) = v825;
            v504 = sqlite3VdbeMemStringify(v7 + 56LL * *((int *)v6 + 1), v13, 0);
          }
          if ( v504 )
            goto LABEL_1542;
          v501 = *(_WORD *)(v500 + 20) & 0xFFFD;
LABEL_989:
          v505 = *(_WORD *)(v502 + 20);
          if ( (v505 & 0x12) != 0 )
          {
            if ( (v505 & 0x400) == 0 )
              goto LABEL_995;
            v506 = sqlite3VdbeMemExpandBlob(v502);
          }
          else
          {
            LOBYTE(v13) = v825;
            v506 = sqlite3VdbeMemStringify(v502, v13, 0);
          }
          if ( !v506 )
          {
            v505 = *(_WORD *)(v502 + 20) & 0xFFFD;
LABEL_995:
            LODWORD(v507) = *(_DWORD *)(v500 + 16) + *(_DWORD *)(v502 + 16);
            if ( (int)v507 > *(_DWORD *)(v833 + 136) )
              goto LABEL_1527;
            if ( !(unsigned int)sqlite3VdbeMemGrow(v503, (unsigned int)(v507 + 2), v503 == v502) )
            {
              v507 = (int)v507;
              *(_WORD *)(v503 + 20) &= 0xF242u;
              *(_WORD *)(v503 + 20) |= 2u;
              if ( v503 != v502 )
              {
                memcpy_0(*(void **)(v503 + 8), *(const void **)(v502 + 8), *(int *)(v502 + 16));
                *(_WORD *)(v502 + 20) = v505;
              }
              memcpy_0(
                (void *)(*(_QWORD *)(v503 + 8) + *(int *)(v502 + 16)),
                *(const void **)(v500 + 8),
                *(int *)(v500 + 16));
              v9 = v825;
              v10 = 1;
              *(_WORD *)(v500 + 20) = v501;
              if ( v825 > 1u )
                v507 = (int)v507 & 0xFFFFFFFFFFFFFFFEuLL;
              v3 = 0;
              v14 = Table;
              *(_BYTE *)(v507 + *(_QWORD *)(v503 + 8)) = 0;
              *(_BYTE *)(*(_QWORD *)(v503 + 8) + v507 + 1) = 0;
              *(_WORD *)(v503 + 20) |= 0x200u;
              *(_DWORD *)(v503 + 16) = v507;
              v4 = a1;
              *(_BYTE *)(v503 + 22) = v825;
              goto LABEL_335;
            }
            goto LABEL_1541;
          }
LABEL_1542:
          v2 = v833;
          goto LABEL_1543;
        }
LABEL_1042:
        if ( *((int *)v6 + 3) > 0 )
        {
          *(_DWORD *)(56LL * *((int *)v6 + 3) + v7 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v6 + 3) + v7 + 8) = &Src;
        }
        v537 = *((int *)v6 + 1);
        v538 = *(_QWORD *)(v4[15] + 8 * v537);
        if ( !v538 || (*(_BYTE *)(v538 + 8) & 8) != 0 || *((_DWORD *)v6 + 2) > *(__int16 *)(v538 + 72) )
        {
          v542 = allocateCursor(v4, v537, *((unsigned int *)v6 + 2), 0);
          v538 = v542;
          if ( !v542 )
            goto LABEL_1543;
          v543 = (_QWORD *)(v542 + 16);
          v824 = 1054;
          *(_DWORD *)(v542 + 8) |= 1u;
          v544 = sqlite3BtreeOpen(*(_QWORD *)v2, 0, v2, v542 + 16);
          v3 = 0;
          v14 = v544;
          if ( v544 )
            goto LABEL_1545;
          v545 = sqlite3BtreeBeginTrans(*v543, 1, 0);
          v3 = 0;
          Table = v545;
          v14 = v545;
          if ( !v545 )
          {
            v546 = *((_QWORD *)v6 + 2);
            v547 = (_DWORD *)(v538 + 68);
            *(_QWORD *)(v538 + 56) = v546;
            if ( v546 )
            {
              v548 = *v543;
              v549 = *((unsigned __int16 *)v6 + 1) | 2;
              sqlite3BtreeEnter(*v543);
              Table = btreeCreateTable(v548, v538 + 68, v549);
              sqlite3BtreeLeave(v548);
              v3 = 0;
              if ( Table )
              {
                v14 = Table;
              }
              else
              {
                v14 = sqlite3BtreeCursor(*v543, *v547, 4, v546, *(_QWORD *)(v538 + 48));
                Table = v14;
                v3 = 0;
              }
              v9 = v825;
              *(_BYTE *)(v538 + 4) = 0;
            }
            else
            {
              v550 = *(_QWORD *)(v538 + 48);
              v551 = *v543;
              *v547 = 1;
              v14 = sqlite3BtreeCursor(v551, 1, 4, 0, v550);
              Table = v14;
              v3 = 0;
              *(_BYTE *)(v538 + 4) = 1;
            }
          }
          *(_DWORD *)(v538 + 8) = *(_DWORD *)(v538 + 8) & 0xFFFFFFFB | (*((_WORD *)v6 + 1) != 8 ? 4 : 0);
          if ( v14 )
          {
            sqlite3BtreeClose(*(_QWORD *)(v538 + 16));
            goto LABEL_1522;
          }
          v4 = a1;
        }
        else
        {
          v539 = *(unsigned int *)(v538 + 68);
          v540 = *(_QWORD *)(v538 + 16);
          *(_QWORD *)(v538 + 24) = 0;
          *(_DWORD *)(v538 + 32) = 0;
          v541 = sqlite3BtreeClearTable(v540, v539, 0);
          v3 = 0;
          Table = v541;
          v14 = v541;
          if ( v541 )
            goto LABEL_1546;
        }
        v10 = 1;
        *(_BYTE *)(v538 + 2) = 1;
        goto LABEL_335;
      }
      if ( (unsigned int)v15 <= 0x81 )
      {
        if ( (_DWORD)v15 == 129 )
        {
          if ( *((_DWORD *)v6 + 3) )
            v598 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
          else
            v598 = 0;
          v71 = sqlite3BtreeTransferRow(
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL),
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2)) + 48LL),
                  v598);
          goto LABEL_153;
        }
        if ( (unsigned int)v15 <= 0x7A )
        {
          if ( (_DWORD)v15 == 122 )
          {
            if ( *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) )
            {
              sqlite3VdbeFreeCursorNN(v4);
              v5 = v828;
              v3 = 0;
              v10 = 1;
            }
            *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) = 0;
            goto LABEL_196;
          }
          v529 = v15 - 117;
          if ( !v529 )
          {
            v552 = out2Prerelease(v4, v6);
            v554 = *((_QWORD *)v6 + 2);
            v555 = v552;
            if ( v554 )
            {
              v557 = -1;
              do
                ++v557;
              while ( *(_BYTE *)(v554 + v557) );
              v556 = v557 & 0x3FFFFFFF;
            }
            else
            {
              v556 = 0;
            }
            *((_DWORD *)v6 + 1) = v556;
            if ( v9 != 1 )
            {
              LOBYTE(v553) = 1;
              Table = sqlite3VdbeMemSetStr(v552, v554, -1, v553, 0);
              v14 = Table;
              if ( Table )
                goto LABEL_1528;
              if ( (unsigned int)sqlite3VdbeChangeEncoding(v555, v9) )
                goto LABEL_1543;
              *(_DWORD *)(v555 + 32) = 0;
              *(_WORD *)(v555 + 20) |= 0x2000u;
              if ( v6[1] == 0xFA && *((_QWORD *)v6 + 2) )
                sqlite3DbFreeNN(v2);
              v6[1] = -6;
              *((_QWORD *)v6 + 2) = *(_QWORD *)(v555 + 8);
              v556 = *(_DWORD *)(v555 + 16);
              *((_DWORD *)v6 + 1) = v556;
            }
            if ( v556 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            *v6 = 73;
LABEL_1075:
            v558 = out2Prerelease(v4, v6);
            v3 = 0;
            *(_WORD *)(v558 + 20) = 8706;
            *(_QWORD *)(v558 + 8) = *((_QWORD *)v6 + 2);
            *(_DWORD *)(v558 + 16) = *((_DWORD *)v6 + 1);
            *(_BYTE *)(v558 + 22) = v9;
            if ( *((int *)v6 + 3) <= 0 )
            {
LABEL_1408:
              v10 = 1;
              goto LABEL_1404;
            }
            v10 = 1;
            v13 = v826;
            if ( *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) == *((unsigned __int16 *)v6 + 1) )
            {
              *(_WORD *)(v558 + 20) = 8720;
              goto LABEL_1078;
            }
            goto LABEL_623;
          }
          v530 = v529 - 1;
          if ( v530 )
          {
            v531 = v530 - 1;
            if ( v531 )
            {
              v532 = v531 - 1;
              if ( v532 )
              {
                if ( v532 != 1 )
                  goto LABEL_53;
                LOBYTE(v16) = 3;
                v533 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 3), v16);
                v3 = 0;
                if ( !v533 )
                  goto LABEL_1543;
                v10 = 1;
                *(_BYTE *)(v533 + 2) = 1;
                *(_DWORD *)(v533 + 36) = *((_DWORD *)v6 + 2);
                *(_QWORD *)(v533 + 48) = byte_180159FC0;
                *(_BYTE *)(v533 + 4) = 1;
                goto LABEL_195;
              }
              v534 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
              v535 = *(_QWORD *)(v534 + 24);
              *(_QWORD *)(v534 + 24) = v535 + 1;
              if ( v535 )
                goto LABEL_196;
              goto LABEL_1219;
            }
            LOBYTE(v16) = v10;
            v536 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 2), v16);
            if ( !v536 )
              goto LABEL_1543;
            *(_QWORD *)(v536 + 56) = *((_QWORD *)v6 + 2);
            v71 = sqlite3VdbeSorterInit(v2, *((unsigned int *)v6 + 3), v536);
            goto LABEL_153;
          }
          goto LABEL_1042;
        }
        v559 = v15 - 124;
        if ( !v559 )
        {
          v589 = *((int *)v6 + 7);
          *(_QWORD *)&v840 = 0;
          v590 = v4[15];
          LODWORD(v832) = 0;
          v838 = 0;
          v839 = 0;
          v591 = *(_QWORD *)(v590 + 8 * v589);
          if ( **(_BYTE **)(v591 + 48) )
            goto LABEL_53;
          v592 = *((_DWORD *)v6 + 1);
          *(_QWORD *)&v838 = *(_QWORD *)(v591 + 56);
          WORD6(v839) = *((_WORD *)v6 + 20);
          v593 = *((int *)v6 + 9);
          BYTE14(v839) = 0;
          *((_QWORD *)&v838 + 1) = v7 + 56 * v593;
          while ( 1 )
          {
            v594 = sqlite3VdbeIdxKeyCompare(v2, v591, &v838, &v832);
            v3 = 0;
            Table = v594;
            v14 = v594;
            if ( v594 )
              goto LABEL_1546;
            v595 = (int)v832 < 0;
            if ( (int)v832 > 0 )
            {
              if ( !*((_WORD *)v6 + 1) )
                goto LABEL_1149;
              v595 = (int)v832 < 0;
            }
            if ( !v595 )
              goto LABEL_1218;
            if ( v592 <= 0 )
              goto LABEL_1408;
            v596 = *(_QWORD *)(v591 + 48);
            *(_DWORD *)(v591 + 32) = 0;
            v597 = sqlite3BtreeNext(v596, 0);
            v3 = 0;
            v14 = v597;
            if ( v597 )
              break;
            --v592;
          }
          if ( v597 != 101 )
            goto LABEL_1546;
          v14 = 0;
          Table = 0;
LABEL_1149:
          v9 = v825;
          v6 += 24;
          goto LABEL_213;
        }
        v560 = v559 - 1;
        if ( !v560 )
        {
          v587 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v588 = *(unsigned __int16 *)(v587 + 12);
          if ( v588 >= *((_DWORD *)v6 + 2) )
          {
            if ( v588 > *((_DWORD *)v6 + 3) )
              *(_WORD *)(v587 + 12) = *((_WORD *)v6 + 6);
            v13 = v826;
            goto LABEL_53;
          }
          *(_WORD *)(v587 + 12) = *((_WORD *)v6 + 4);
LABEL_196:
          v13 = v826;
          goto LABEL_53;
        }
        v561 = v560 - 1;
        if ( !v561 )
        {
          v585 = (_QWORD *)out2Prerelease(v4, v6);
          v10 = 1;
          *v585 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 24LL);
          v586 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          ++*(_QWORD *)(v586 + 24);
          goto LABEL_60;
        }
        v562 = v561 - 1;
        if ( !v562 )
        {
          v832 = 0;
          LODWORD(v834) = 0;
          v576 = (__int64 *)out2Prerelease(v4, v6);
          v577 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( (*(_BYTE *)(v577 + 8) & 2) != 0 )
          {
            v3 = 0;
          }
          else
          {
            v578 = sqlite3BtreeLast(*(_QWORD *)(v577 + 48), &v834);
            v3 = 0;
            Table = v578;
            v14 = v578;
            if ( v578 )
              goto LABEL_1546;
            if ( (_DWORD)v834 )
            {
              v832 = 1;
            }
            else
            {
              v579 = sqlite3BtreeIntegerKey(*(_QWORD *)(v577 + 48));
              v832 = v579;
              if ( v579 == 0x7FFFFFFFFFFFFFFFLL )
                *(_DWORD *)(v577 + 8) |= 2u;
              else
                v832 = v579 + 1;
              v3 = 0;
            }
          }
          if ( *((_DWORD *)v6 + 3) )
          {
            v580 = v4[33];
            if ( v580 )
            {
              while ( *(_QWORD *)(v580 + 8) )
                v580 = *(_QWORD *)(v580 + 8);
              v581 = (__int64 *)(*(_QWORD *)(v580 + 24) + 56LL * *((int *)v6 + 3));
            }
            else
            {
              v581 = (__int64 *)(v829 + 56LL * *((int *)v6 + 3));
            }
            sqlite3VdbeMemIntegerify(v581);
            if ( *v581 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v577 + 8) & 2) != 0 )
            {
              v14 = 13;
              goto LABEL_1523;
            }
            v582 = v832;
            if ( v832 < *v581 + 1 )
            {
              v582 = *v581 + 1;
              v832 = v582;
            }
            *v581 = v582;
            v3 = 0;
          }
          if ( (*(_BYTE *)(v577 + 8) & 2) != 0 )
          {
            v583 = 0;
            while ( 1 )
            {
              sqlite3_randomness(8, &v832);
              v832 = (v832 & 0x3FFFFFFFFFFFFFFFLL) + 1;
              v584 = sqlite3BtreeTableMoveto(*(_QWORD *)(v577 + 48), v832, 0, &v834);
              v3 = 0;
              Table = v584;
              v14 = v584;
              if ( v584 )
                goto LABEL_1546;
              if ( (_DWORD)v834 )
                break;
              if ( ++v583 >= 100 )
              {
                v14 = 13;
                goto LABEL_1546;
              }
            }
          }
          *(_BYTE *)(v577 + 3) = 0;
          *(_DWORD *)(v577 + 32) = 0;
          *v576 = v832;
          goto LABEL_79;
        }
        if ( v562 != 1 )
          goto LABEL_53;
        v563 = *((int *)v6 + 1);
        v564 = 56LL * *((int *)v6 + 2);
        v838 = 0;
        v839 = 0;
        v565 = v4[15];
        v840 = 0;
        v566 = *(_QWORD *)(v565 + 8 * v563);
        v72 = v6[1] == 0xFB;
        v567 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
        *((_QWORD *)&v838 + 1) = v567;
        if ( v72 && *(_QWORD *)(v2 + 320) )
        {
          v568 = *((_QWORD *)v6 + 2);
          v569 = *(_QWORD *)(32LL * *(char *)(v566 + 1) + *(_QWORD *)(v2 + 32));
        }
        else
        {
          v568 = 0;
          v569 = 0;
        }
        if ( ((unsigned __int8)v10 & v6[2]) != 0 )
        {
          v4[7] += v10;
          if ( (v6[2] & 0x20) != 0 )
            *(_QWORD *)(v2 + 56) = v567;
        }
        v570 = *((_WORD *)v6 + 1);
        *(_QWORD *)&v839 = *(_QWORD *)(v564 + v829 + 8);
        DWORD1(v840) = *(_DWORD *)(v564 + v829 + 16);
        if ( (v570 & 0x10) != 0 )
          v571 = *(unsigned int *)(v566 + 36);
        else
          v571 = 0;
        if ( (*(_WORD *)(v564 + v829 + 20) & 0x400) != 0 )
          DWORD2(v840) = *(_DWORD *)(v564 + v829);
        else
          DWORD2(v840) = 0;
        *(_QWORD *)&v838 = 0;
        v572 = sqlite3BtreeInsert(*(_QWORD *)(v566 + 48), &v838, (unsigned __int8)v570 & 0x8A, v571);
        v3 = 0;
        Table = v572;
        *(_BYTE *)(v566 + 3) = 0;
        v14 = v572;
        *(_DWORD *)(v566 + 32) = 0;
        if ( v572 )
          goto LABEL_1546;
        v10 = 1;
        ++v841;
        if ( !v568 )
          goto LABEL_1403;
        v573 = *((_QWORD *)&v838 + 1);
        v574 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int))(v2 + 320);
        v575 = (v6[2] & 4) != 0 ? 23 : 18;
LABEL_1103:
        v574(*(_QWORD *)(v2 + 312), v575, v569, *(_QWORD *)v568, v573, v824);
        goto LABEL_421;
      }
      if ( (unsigned int)v15 > 0x87 )
      {
        switch ( (_DWORD)v15 )
        {
          case 0x88:
            v645 = *((int *)v6 + 1);
            v646 = *(_QWORD *)(v4[15] + 8 * v645);
            if ( !v646 )
            {
              LOBYTE(v16) = 3;
              v646 = allocateCursor(v4, v645, (unsigned int)v10, v16);
              if ( !v646 )
                goto LABEL_1543;
              *(_DWORD *)(v646 + 8) |= 8u;
              *(_DWORD *)(v646 + 36) = 0;
              *(_BYTE *)(v646 + 4) = 1;
              valid = sqlite3BtreeFakeValidCursor();
              v3 = 0;
              *(_QWORD *)(v646 + 48) = valid;
              v10 = 1;
            }
            *(_BYTE *)(v646 + 2) = v10;
            *(_DWORD *)(v646 + 32) = 0;
            if ( !*(_BYTE *)v646 )
            {
              sqlite3BtreeClearCursor(*(_QWORD *)(v646 + 48));
              goto LABEL_244;
            }
            goto LABEL_1404;
          case 0x89:
            goto LABEL_1211;
          case 0x8A:
            v630 = v4[15];
            v631 = *((int *)v6 + 1);
            v838 = 0;
            v839 = 0;
            v840 = 0;
            v632 = *(_QWORD *)(v630 + 8 * v631);
            v633 = v7 + 56LL * *((int *)v6 + 2);
            if ( ((unsigned __int8)v10 & v6[2]) != 0 )
              v4[7] += v10;
            if ( (*(_WORD *)(v633 + 20) & 0x400) != 0 )
            {
              v634 = sqlite3VdbeMemExpandBlob(v633);
              v3 = 0;
              v14 = v634;
              if ( v634 )
                goto LABEL_1546;
            }
            v635 = *((_WORD *)v6 + 1);
            *((_QWORD *)&v838 + 1) = *(int *)(v633 + 16);
            *(_QWORD *)&v838 = *(_QWORD *)(v633 + 8);
            v636 = v7 + 56LL * *((int *)v6 + 3);
            LOWORD(v840) = *((_WORD *)v6 + 8);
            *((_QWORD *)&v839 + 1) = v636;
            if ( (v635 & 0x10) != 0 )
              v637 = *(unsigned int *)(v632 + 36);
            else
              v637 = 0;
            v629 = sqlite3BtreeInsert(*(_QWORD *)(v632 + 48), &v838, (unsigned __int8)v635 & 0x8A, v637);
            v3 = 0;
            *(_DWORD *)(v632 + 32) = 0;
            break;
          default:
            v626 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v627 = v7 + 56LL * *((int *)v6 + 2);
            if ( (*(_WORD *)(v627 + 20) & 0x400) != 0 )
            {
              v628 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              v14 = v628;
              if ( v628 )
                goto LABEL_1546;
            }
            v629 = sqlite3VdbeSorterWrite(v626, v627);
            v3 = 0;
            break;
        }
        Table = v629;
        v14 = v629;
        v170 = v629 == 0;
LABEL_326:
        if ( !v170 )
          goto LABEL_1546;
        goto LABEL_80;
      }
      if ( (_DWORD)v15 != 135 )
      {
        v599 = v15 - 130;
        if ( v599 )
        {
          v600 = v599 - 1;
          if ( !v600 )
          {
            sqlite3VdbeSetChanges(v2, v4[7]);
            v3 = 0;
            v4[7] = 0;
            goto LABEL_52;
          }
          v601 = v600 - 1;
          if ( v601 )
          {
            v602 = v601 - 1;
            if ( !v602 )
            {
              v608 = sqlite3VdbeSorterRowkey(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)), v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              Table = v608;
              v14 = v608;
              if ( v608 )
                goto LABEL_1546;
              *(_DWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3)) + 32LL) = 0;
              goto LABEL_52;
            }
            if ( v602 != 1 )
              goto LABEL_53;
            v603 = out2Prerelease(v4, v6);
            v604 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL);
            v605 = sqlite3BtreePayloadSize(v604);
            if ( v605 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            v606 = sqlite3VdbeMemFromBtreeZeroOffset(v604, v605, v603);
            v3 = 0;
            Table = v606;
            v14 = v606;
            if ( v606 )
              goto LABEL_1546;
            if ( !*((_DWORD *)v6 + 3) && (*(_WORD *)(v603 + 20) & 0x4000) != 0 )
            {
              Writeable = sqlite3VdbeMemMakeWriteable(v603);
              v3 = 0;
              if ( Writeable )
                goto LABEL_1543;
              goto LABEL_80;
            }
            goto LABEL_1408;
          }
          v609 = v4[15];
          v610 = *((unsigned int *)v6 + 4);
          v611 = 56LL * *((int *)v6 + 3);
          v612 = *((int *)v6 + 1);
          LODWORD(v832) = 0;
          v613 = sqlite3VdbeSorterCompare(*(_QWORD *)(v609 + 8 * v612), v7 + v611, v610, &v832);
          v3 = 0;
          Table = v613;
          v14 = v613;
          if ( v613 )
            goto LABEL_1546;
          v105 = (_DWORD)v832 == 0;
          goto LABEL_194;
        }
        v614 = *((_DWORD *)v6 + 2);
        v615 = *(_QWORD *)(a1[15] + 8LL * *((int *)v6 + 1));
        if ( v6[1] == 0xFB && *(_QWORD *)(v2 + 320) )
        {
          v568 = *((_QWORD *)v6 + 2);
          v569 = *(_QWORD *)(32LL * *(char *)(v615 + 1) + *(_QWORD *)(v2 + 32));
          if ( (v6[2] & 2) != 0 && *(_BYTE *)(v615 + 4) )
            *(_QWORD *)(v615 + 80) = sqlite3BtreeIntegerKey(*(_QWORD *)(v615 + 48));
        }
        else
        {
          v569 = 0;
          v568 = 0;
        }
        LOBYTE(v13) = v6[2];
        v616 = sqlite3BtreeDelete(*(_QWORD *)(v615 + 48), v13);
        v3 = 0;
        Table = v616;
        *(_QWORD *)(v615 + 32) = 0;
        v14 = v616;
        if ( v616 )
          goto LABEL_1545;
        v10 = 1;
        ++v841;
        v72 = (v614 & 1) == 0;
        v4 = a1;
        if ( v72 )
          goto LABEL_1403;
        ++a1[7];
        v574 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, int))(v2 + 320);
        if ( !v574 || !v568 || *(char *)(v568 + 48) < 0 )
          goto LABEL_1403;
        v573 = *(_QWORD *)(v615 + 80);
        v575 = v14 + 9;
        goto LABEL_1103;
      }
      v842 = 0;
      v617 = out2Prerelease(v4, v6);
      v618 = *((int *)v6 + 1);
      v3 = 0;
      v619 = v4[15];
      v620 = v617;
      v621 = *(_QWORD *)(v619 + 8 * v618);
      if ( *(_BYTE *)(v621 + 2) )
      {
        v10 = 1;
        *(_WORD *)(v617 + 20) = 1;
        goto LABEL_146;
      }
      if ( *(_BYTE *)(v621 + 3) )
      {
        v622 = *(_QWORD *)(v621 + 80);
      }
      else if ( *(_BYTE *)v621 == 2 )
      {
        v623 = *(__int64 **)(v621 + 48);
        v624 = *v623;
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*(_QWORD *)*v623 + 96LL))(v623, &v842);
        v14 = Table;
        sqlite3VtabImportErrmsg(v4, v624);
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        v622 = v842;
      }
      else
      {
        v625 = sqlite3VdbeCursorRestore(*(_QWORD *)(v619 + 8 * v618));
        v3 = 0;
        Table = v625;
        v14 = v625;
        if ( v625 )
          goto LABEL_1546;
        if ( *(_BYTE *)(v621 + 2) )
        {
          v10 = 1;
          *(_WORD *)(v620 + 20) = 1;
          goto LABEL_146;
        }
        v622 = sqlite3BtreeIntegerKey(*(_QWORD *)(v621 + 48));
        v3 = 0;
      }
LABEL_1195:
      *(_QWORD *)v620 = v622;
      goto LABEL_80;
    }
    if ( (unsigned int)v15 > 0xA3 )
    {
      if ( (unsigned int)v15 <= 0xAE )
      {
        if ( (_DWORD)v15 == 174 )
        {
          v760 = *((int *)v6 + 2);
          v831 = 0;
          v761 = v7 + 56 * v760;
          sqlite3VdbeMemSetNull(v761);
          v762 = (_QWORD *)*((_QWORD *)v6 + 2);
          v3 = 0;
          v763 = v762[10];
          if ( !v763 )
            goto LABEL_1406;
          v764 = *(__int64 **)(v763 + 16);
          v765 = *v764;
          sqlite3VtabLock();
          v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, unsigned int **))(v765 + 192))(
                  v764,
                  *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32)),
                  *v762,
                  *((unsigned int *)v6 + 3),
                  &v831);
          Table = v14;
          sqlite3VtabUnlock(v762[10]);
          v3 = 0;
          if ( v14 )
          {
            sqlite3_free(v831);
            goto LABEL_1522;
          }
          if ( !v831 )
          {
LABEL_1406:
            v4 = a1;
LABEL_1407:
            v7 = v829;
            goto LABEL_1408;
          }
          LOBYTE(v766) = 1;
          sqlite3VdbeMemSetStr(v761, v831, -1, v766, sqlite3_free);
          goto LABEL_854;
        }
        if ( (unsigned int)v15 <= 0xA9 )
        {
          if ( (_DWORD)v15 != 169 )
          {
            v742 = v15 - 164;
            if ( v742 )
            {
              v743 = v742 - 1;
              if ( v743 )
              {
                v744 = v743 - 1;
                if ( v744 )
                {
                  v745 = v744 - 1;
                  if ( v745 )
                  {
                    if ( v745 != 1 )
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
            v746 = v7 + 56LL * *((int *)v6 + 1);
            if ( *((_DWORD *)v6 + 3) )
            {
              v14 = sqlite3VdbeMemAggValue(v746, v7 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2));
              Table = v14;
              v746 = v7 + 56LL * *((int *)v6 + 3);
            }
            else
            {
              v14 = sqlite3VdbeMemFinalize(v746, *((_QWORD *)v6 + 2));
              Table = v14;
            }
            if ( !v14 )
            {
              sqlite3VdbeChangeEncoding(v746, v9);
              goto LABEL_244;
            }
            v808 = (const char *)sqlite3_value_text(v746);
            v809 = "%s";
            goto LABEL_1538;
          }
          if ( v6[12] || (*(_QWORD *)(v2 + 48) & 0x400000000LL) == 0 )
          {
            v747 = sqlite3BtreeLockTable(
                     *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8),
                     *((unsigned int *)v6 + 2));
            v3 = 0;
            Table = v747;
            v14 = v747;
            if ( v747 )
            {
              if ( (_BYTE)v747 != 6 )
                goto LABEL_1546;
              sqlite3VdbeError(v4, "database table is locked: %s", *((_QWORD *)v6 + 2));
              goto LABEL_1523;
            }
            goto LABEL_52;
          }
          goto LABEL_1078;
        }
        v748 = v15 - 170;
        if ( v748 )
        {
          v749 = v748 - 1;
          if ( v749 )
          {
            v750 = v749 - 1;
            if ( v750 )
            {
              if ( v750 != 1 )
                goto LABEL_53;
              v751 = *((_QWORD *)v6 + 2);
              v831 = 0;
              v752 = *(__int64 **)(v751 + 16);
              if ( v752 )
              {
                v753 = *v752;
                if ( *v752 )
                {
                  Table = (*(__int64 (__fastcall **)(__int64 *, unsigned int **))(v753 + 48))(v752, &v831);
                  v14 = Table;
                  sqlite3VtabImportErrmsg(v4, v752);
                  v3 = 0;
                  if ( Table )
                    goto LABEL_1546;
                  LOBYTE(v754) = 2;
                  *(_QWORD *)v831 = v752;
                  v755 = allocateCursor(v4, *((unsigned int *)v6 + 1), 0, v754);
                  v3 = 0;
                  if ( v755 )
                  {
                    v10 = 1;
                    *(_QWORD *)(v755 + 48) = v831;
                    ++*((_DWORD *)v752 + 2);
                    goto LABEL_146;
                  }
                  (*(void (__fastcall **)(unsigned int *))(v753 + 56))(v831);
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
          v850 = 0;
          v756 = *((int *)v6 + 2);
          *(_QWORD *)&v848 = 0;
          v847 = 0;
          v849 = 0;
          *((_QWORD *)&v848 + 1) = v2;
          Table = sqlite3VdbeMemCopy(&v847, v7 + 56 * v756);
          v14 = Table;
          v757 = sqlite3_value_text(&v847);
          if ( v757 )
          {
            v14 = sqlite3VtabCallCreate(v2, *((unsigned int *)v6 + 1), v757, v4 + 21);
            Table = v14;
          }
          sqlite3VdbeMemRelease(&v847);
        }
        else
        {
          v758 = *((_QWORD *)v6 + 2);
          v759 = sqlite3VtabBegin(v2, v758);
          v3 = 0;
          Table = v759;
          v14 = v759;
          if ( !v758 )
            goto LABEL_1246;
          sqlite3VtabImportErrmsg(v4, *(_QWORD *)(v758 + 16));
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
        v767 = v15 - 175;
        if ( !v767 )
        {
          v788 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v789 = (_QWORD *)sqlite3_malloc64(16);
          v790 = v789;
          if ( v789 )
          {
            *v789 = *(_QWORD *)(v788 + 48);
            v789[1] = v7 + 56LL * *((int *)v6 + 3);
            v791 = out2Prerelease(v4, v6);
            *(_WORD *)(v791 + 20) = 1;
            sqlite3VdbeMemSetPointer(v791, v790, "ValueList", sqlite3VdbeValueListFree);
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        v768 = v767 - 1;
        if ( !v768 )
        {
          v857 = 0;
          v859 = 0;
          memset(v855, 0, sizeof(v855));
          v860 = 0;
          v856 = 0;
          memset_0(&v858, 0, 0x45u);
          v780 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v781 = *((int *)v6 + 3);
          v782 = v7 + 56 * v781;
          if ( *(_BYTE *)(v780 + 2) )
          {
            sqlite3VdbeMemSetNull(v7 + 56 * v781);
            goto LABEL_422;
          }
          v783 = **(__int64 ***)(v780 + 48);
          v784 = *v783;
          BYTE8(v856) = v825;
          *((_QWORD *)&v855[0] + 1) = &v858;
          *(_QWORD *)&v855[0] = v782;
          v861 = 0x1000000;
          if ( (v6[2] & 1) != 0 )
          {
            sqlite3VdbeMemSetNull(v782);
            v785 = 1025;
            *(_DWORD *)v782 = 0;
          }
          else
          {
            v785 = *(_WORD *)(v782 + 20) & 0xF240 | 1;
          }
          *(_WORD *)(v782 + 20) = v785;
          v786 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v784 + 88))(
                   *(_QWORD *)(v780 + 48),
                   v855,
                   *((unsigned int *)v6 + 2));
          v4 = a1;
          Table = v786;
          v14 = v786;
          sqlite3VtabImportErrmsg(a1, v783);
          if ( SDWORD1(v856) > 0 )
          {
            v787 = (const char *)sqlite3_value_text(v782);
            sqlite3VdbeError(a1, "%s", v787);
            v14 = DWORD1(v856);
            Table = DWORD1(v856);
          }
          v9 = v825;
          sqlite3VdbeChangeEncoding(v782, v825);
          goto LABEL_50;
        }
        v769 = v768 - 1;
        if ( v769 )
        {
          v770 = v769 - 1;
          if ( v770 )
          {
            if ( v770 != 1 )
              goto LABEL_53;
            v771 = (_QWORD *)out2Prerelease(v4, v6);
            v772 = 32LL * *((int *)v6 + 1);
            v773 = *(_QWORD *)(v772 + *(_QWORD *)(v2 + 32) + 8);
            Page = 0;
            if ( *((_DWORD *)v6 + 3) )
            {
              Page = sqlite3BtreeLastPage(*(_QWORD *)(v772 + *(_QWORD *)(v2 + 32) + 8));
              if ( Page < *((_DWORD *)v6 + 3) )
                Page = *((_DWORD *)v6 + 3);
            }
            *v771 = (unsigned int)sqlite3BtreeMaxPageCount(v773, Page);
            goto LABEL_422;
          }
          v775 = (_QWORD *)out2Prerelease(v4, v6);
          *v775 = (unsigned int)sqlite3BtreeLastPage(*(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8));
LABEL_244:
          v3 = 0;
          goto LABEL_52;
        }
        v776 = *(_DWORD *)(v2 + 48);
        *(_QWORD *)(v2 + 48) |= 0x4000000uLL;
        v777 = *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL);
        v778 = v829 + 56LL * *((int *)v6 + 1);
        v779 = sqlite3VdbeChangeEncoding(v778, (unsigned int)v10);
        v3 = 0;
        v14 = v779;
        if ( v779 )
          goto LABEL_1546;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v777 + 152LL))(v777, *(_QWORD *)(v778 + 8));
        v14 = Table;
        if ( (v776 & 0x4000000) == 0 )
          *(_QWORD *)(v2 + 48) &= ~0x4000000uLL;
        sqlite3VtabImportErrmsg(v4, v777);
        *((_DWORD *)v4 + 50) &= 0xFFFFFFFC;
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        goto LABEL_79;
      }
      v792 = v15 - 181;
      if ( v792 )
      {
        v793 = v792 - 1;
        if ( !v793 )
        {
          v805 = 56LL * *((int *)v6 + 1);
          v806 = 56LL * *((int *)v6 + 2);
          if ( ((unsigned __int8)v10 & *(_BYTE *)(v805 + v7 + 20)) != 0 )
          {
            *(_WORD *)(v806 + v7 + 20) &= ~0x800u;
          }
          else
          {
            *(_WORD *)(v806 + v7 + 20) |= 0x800u;
            *(_BYTE *)(v806 + v7 + 23) = *(_BYTE *)(v805 + v7);
          }
          goto LABEL_196;
        }
        v794 = v793 - 1;
        if ( !v794 )
        {
          v802 = 56LL * *((int *)v6 + 1);
          v803 = filterHash(v7, v6);
          v804 = (v803 % (8 * *(_DWORD *)(v802 + v7 + 16))) >> 3;
          *(_BYTE *)(v804 + *(_QWORD *)(v802 + v7 + 8)) |= 1 << ((v803 % (8 * *(_DWORD *)(v802 + v7 + 16))) & 7);
          goto LABEL_244;
        }
        if ( v794 != 1 )
          goto LABEL_53;
        goto LABEL_1442;
      }
      v807 = 56LL * *((int *)v6 + 1);
      v677 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v807 + v7 + 20) & 0x800) != 0 )
      {
        sqlite3VdbeMemSetInt64(v677, *(unsigned __int8 *)(v807 + v7 + 23));
        goto LABEL_244;
      }
LABEL_1260:
      sqlite3VdbeMemSetNull(v677);
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
            v678 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( *(_BYTE *)v678 == (_BYTE)v10 )
            {
              sqlite3VdbeSorterReset(v2, *(_QWORD *)(v678 + 48));
              goto LABEL_244;
            }
            v71 = sqlite3BtreeClearTableOfCursor(*(_QWORD *)(v678 + 48));
            goto LABEL_153;
          }
          v657 = v15 - 141;
          if ( v657 )
          {
            v658 = v657 - 1;
            if ( v658 )
            {
              v659 = v658 - 1;
              if ( !v659 )
              {
                v670 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
                if ( !*(_BYTE *)(v670 + 3) )
                  goto LABEL_53;
                v71 = sqlite3VdbeFinishMoveto(v670);
                goto LABEL_153;
              }
              v660 = v659 - 1;
              if ( !v660 )
              {
                LODWORD(v834) = 0;
                v666 = out2Prerelease(v4, v6);
                *(_WORD *)(v666 + 20) = 1;
                if ( *(_DWORD *)(v2 + 220) > *(_DWORD *)(v2 + 232) + 1 )
                {
                  v14 = 6;
                  *((_BYTE *)v4 + 196) = 2;
                  goto LABEL_1523;
                }
                v667 = *((_DWORD *)v6 + 3);
                v668 = *(_QWORD *)(v2 + 32);
                v669 = *((unsigned int *)v6 + 1);
                LODWORD(v834) = 0;
                v14 = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v667 + v668 + 8), v669, &v834);
                Table = v14;
                v3 = 0;
                *(_WORD *)(v666 + 20) = 4;
                *(_QWORD *)v666 = (int)v834;
                if ( v14 )
                  goto LABEL_1546;
                if ( (_DWORD)v834 )
                {
                  sqlite3RootPageMoved(v2, v667, (unsigned int)v834, *((unsigned int *)v6 + 1));
                  v10 = 1;
                  v836 = v667 + 1;
LABEL_59:
                  v9 = v825;
LABEL_60:
                  v5 = v828;
LABEL_61:
                  v13 = v826;
                  v3 = 0;
                  goto LABEL_53;
                }
                v13 = v826;
                v10 = 1;
                goto LABEL_623;
              }
              if ( v660 != 1 )
                goto LABEL_53;
              v661 = *(_QWORD *)(v2 + 32);
              v662 = *((unsigned int *)v6 + 1);
              v663 = 32LL * *((int *)v6 + 2);
              v842 = 0;
              v664 = sqlite3BtreeClearTable(*(_QWORD *)(v663 + v661 + 8), v662, &v842);
              v3 = 0;
              Table = v664;
              v14 = v664;
              if ( *((_DWORD *)v6 + 3) )
              {
                v665 = v842;
                v4[7] += v842;
                if ( *((int *)v6 + 3) > 0 )
                  *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) += v665;
              }
              goto LABEL_1246;
            }
          }
          v671 = *((int *)v6 + 1);
          v672 = v4[15];
          v831 = 0;
          v673 = *(_QWORD *)(v672 + 8 * v671);
          v674 = sqlite3VdbeCursorRestore(v673);
          v3 = 0;
          Table = v674;
          v14 = v674;
          if ( v674 )
            goto LABEL_1546;
          if ( !*(_BYTE *)(v673 + 2) )
          {
            v831 = 0;
            v675 = sqlite3VdbeIdxRowid(v2, *(_QWORD *)(v673 + 48), &v831);
            v3 = 0;
            Table = v675;
            v14 = v675;
            if ( v675 )
              goto LABEL_1546;
            if ( *v6 == 0x8D )
            {
              v10 = v675 + 1;
              v676 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3));
              *(_BYTE *)(v676 + 2) = 0;
              *(_QWORD *)(v676 + 80) = v831;
              *(_BYTE *)(v676 + 3) = v675 + 1;
              *(_DWORD *)(v676 + 32) = 0;
              *(_QWORD *)(v676 + 16) = *((_QWORD *)v6 + 2);
              *(_QWORD *)(v676 + 40) = v673;
              goto LABEL_195;
            }
            v283 = (unsigned int **)out2Prerelease(v4, v6);
            v284 = v831;
            goto LABEL_536;
          }
          v677 = v7 + 56LL * *((int *)v6 + 2);
          goto LABEL_1260;
        }
        v679 = v15 - 147;
        if ( !v679 )
        {
          LODWORD(v832) = 0;
          v695 = out2Prerelease(v4, v6);
          v696 = *(_QWORD *)(v2 + 32);
          v697 = (_QWORD *)v695;
          v698 = *((unsigned int *)v6 + 3);
          v699 = 32LL * *((int *)v6 + 1);
          LODWORD(v832) = 0;
          v700 = sqlite3BtreeCreateTable(*(_QWORD *)(v699 + v696 + 8), &v832, v698);
          v3 = 0;
          Table = v700;
          v14 = v700;
          if ( v700 )
            goto LABEL_1546;
          *v697 = (unsigned int)v832;
          goto LABEL_52;
        }
        v680 = v679 - 1;
        if ( !v680 )
        {
          *(_BYTE *)(v2 + 112) += v10;
          v690 = *(_QWORD *)(v2 + 512);
          v691 = *(_BYTE *)(v2 + 110);
          v692 = *(_DWORD *)(v2 + 744);
          v831 = 0;
          if ( ((unsigned __int8)v10 & v6[4]) != 0 )
          {
            *(_QWORD *)(v2 + 512) = 0;
            *(_BYTE *)(v2 + 110) = 0;
          }
          if ( (v6[4] & 2) != 0 )
            *(_DWORD *)(v2 + 744) = *((_DWORD *)v6 + 2);
          v693 = sqlite3_exec(v2, *((_QWORD *)v6 + 2), 0, 0, (__int64)&v831);
          v694 = (const char *)v831;
          v3 = 0;
          --*(_BYTE *)(v2 + 112);
          v14 = v693;
          Table = v693;
          *(_QWORD *)(v2 + 512) = v690;
          *(_BYTE *)(v2 + 110) = v691;
          *(_DWORD *)(v2 + 744) = v692;
          if ( !v694 && !v693 )
            goto LABEL_79;
          sqlite3VdbeError(v4, "%s", v694);
          sqlite3_free(v831);
LABEL_1288:
          if ( v14 != 7 )
            goto LABEL_1523;
          goto LABEL_1543;
        }
        v681 = v680 - 1;
        if ( v681 )
        {
          v682 = v681 - 1;
          if ( v682 )
          {
            if ( v682 != 1 )
              goto LABEL_53;
            sqlite3UnlinkAndDeleteTable(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
            goto LABEL_244;
          }
          v71 = sqlite3AnalysisLoad(v2, *((unsigned int *)v6 + 1));
          goto LABEL_153;
        }
        v683 = *((int *)v6 + 1);
        v684 = *(_QWORD *)(v2 + 32);
        v838 = 0;
        *(_QWORD *)&v840 = 0;
        v839 = 0;
        if ( *((_QWORD *)v6 + 2) )
        {
          LODWORD(v839) = v683;
          *(_QWORD *)&v838 = v2;
          *((_QWORD *)&v838 + 1) = v4 + 21;
          DWORD2(v839) = 0;
          v686 = 32 * v683;
          v687 = sqlite3BtreeLastPage(*(_QWORD *)(v684 + v686 + 8));
          v688 = *(_QWORD *)(v2 + 32);
          LODWORD(v840) = v687;
          v689 = sqlite3MPrintf(
                   v2,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(v688 + v686),
                   "sqlite_master",
                   *((_QWORD *)v6 + 2));
          if ( !v689 )
          {
            v14 = 7;
LABEL_1533:
            sqlite3ResetAllSchemasOfConnection(v2);
            goto LABEL_1288;
          }
          *(_BYTE *)(v2 + 197) = 1;
          DWORD1(v839) = 0;
          HIDWORD(v839) = 0;
          v14 = sqlite3_exec(v2, v689, (unsigned int)sqlite3InitCallback, (unsigned int)&v838, 0);
          Table = v14;
          if ( !v14 )
          {
            v14 = DWORD1(v839);
            Table = DWORD1(v839);
            if ( !DWORD1(v839) && !HIDWORD(v839) )
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
          sqlite3SchemaClear(*(_QWORD *)(32 * v683 + v684 + 24));
          *(_DWORD *)(v2 + 44) &= ~0x10u;
          inited = sqlite3InitOne(v2, (unsigned int)v683, v4 + 21, *((unsigned __int16 *)v6 + 1));
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
          v720 = *((int *)v6 + 2);
          if ( (*(_DWORD *)(v2 + 48) & 0x80000) != 0 )
          {
            *(_QWORD *)(v2 + 768) += v720;
          }
          else if ( *((_DWORD *)v6 + 1) )
          {
            *(_QWORD *)(v2 + 760) += v720;
          }
          else
          {
            v4[10] += v720;
          }
          goto LABEL_53;
        }
        v701 = v15 - 153;
        if ( !v701 )
        {
          v282 = out2Prerelease(v4, v6);
          *(_WORD *)(v282 + 20) = 8;
          goto LABEL_534;
        }
        v702 = v701 - 1;
        if ( !v702 )
        {
          sqlite3UnlinkAndDeleteTrigger(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
          goto LABEL_244;
        }
        v703 = v702 - 1;
        if ( !v703 )
        {
          v708 = *((int *)v6 + 1);
          v709 = *((_QWORD *)v6 + 2);
          v710 = 56 * v708;
          v711 = v708 + 1;
          LODWORD(v832) = 0;
          v712 = *(_QWORD *)(v2 + 32);
          v713 = 56 * *((_DWORD *)v6 + 3);
          v831 = 0;
          v714 = v7 + 56LL * v711;
          Table = sqlite3BtreeIntegrityCheck(
                    v2,
                    *(_QWORD *)(32LL * *((unsigned __int16 *)v6 + 1) + v712 + 8),
                    (int)v709 + 4,
                    (int)v7 + v713,
                    *((_DWORD *)v6 + 2),
                    (int)v10 + *(_DWORD *)(v710 + v7),
                    (__int64)&v832,
                    (__int64)&v831);
          v14 = Table;
          sqlite3VdbeMemSetNull(v714);
          if ( (_DWORD)v832 )
          {
            if ( Table )
            {
              sqlite3_free(v831);
              goto LABEL_1523;
            }
            LOBYTE(v715) = 1;
            *(_QWORD *)(v710 + v7) -= (int)v832 - 1;
            sqlite3VdbeMemSetStr(v714, v831, -1, v715, sqlite3_free);
          }
          v9 = v825;
          sqlite3VdbeChangeEncoding(v714, v825);
          goto LABEL_1308;
        }
        v704 = v703 - 1;
        if ( !v704 )
        {
          v705 = *((int *)v6 + 1);
          v706 = *((int *)v6 + 2);
          v707 = v7 + 56 * v705;
          if ( (*(_BYTE *)(v707 + 20) & 0x10) != 0 || !(unsigned int)sqlite3VdbeMemSetRowSet(v7 + 56 * v705) )
          {
            sqlite3RowSetInsert(*(_QWORD *)(v707 + 8), *(_QWORD *)(56 * v706 + v7));
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        if ( v704 != 1 )
          goto LABEL_53;
        v322 = out2Prerelease(v4, v6);
        v321 = *(_QWORD *)(v4[33] + 24)
             + 56LL * (*((_DWORD *)v6 + 1) + *(_DWORD *)(*(_QWORD *)(v4[33] + 16) + 24LL * *(int *)(v4[33] + 76) + 4));
        goto LABEL_598;
      }
      v721 = v15 - 159;
      if ( !v721 )
      {
        v734 = v4[33];
        if ( v734 )
        {
          while ( *(_QWORD *)(v734 + 8) )
            v734 = *(_QWORD *)(v734 + 8);
          v735 = (_QWORD *)(*(_QWORD *)(v734 + 24) + 56LL * *((int *)v6 + 1));
        }
        else
        {
          v735 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 1));
        }
        sqlite3VdbeMemIntegerify(v735);
        v736 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 2));
        sqlite3VdbeMemIntegerify(v736);
        v3 = 0;
        v13 = v826;
        v10 = 1;
        if ( *v735 < *v736 )
          *v735 = *v736;
        goto LABEL_623;
      }
      v722 = v721 - 1;
      if ( !v722 )
      {
        v729 = *((int *)v6 + 3);
        v730 = 56LL * *((int *)v6 + 1);
        v831 = 0;
        v620 = out2Prerelease(v4, v6);
        v3 = 0;
        v831 = *(unsigned int **)(v730 + v829);
        if ( (__int64)v831 <= 0 )
        {
          v7 = v829;
        }
        else
        {
          v731 = 56 * v729;
          v7 = v829;
          v732 = *(_QWORD *)(v731 + v829);
          if ( v732 <= 0 )
            v732 = 0;
          v733 = sqlite3AddInt64(&v831, v732);
          v3 = 0;
          if ( !v733 )
          {
            v622 = (__int64)v831;
            goto LABEL_1195;
          }
        }
        *(_QWORD *)v620 = -1;
        goto LABEL_80;
      }
      if ( (unsigned int)(v722 - 1) > 1 )
        goto LABEL_53;
      v723 = *((unsigned __int16 *)v6 + 1);
      v724 = sqlite3DbMallocRawNN(v2, 8 * v723 + 104);
      if ( !v724 )
        goto LABEL_1543;
      *(_QWORD *)(v724 + 16) = 0;
      v725 = v724 + 8 * (v723 + 6);
      *(_QWORD *)v724 = v725;
      sqlite3VdbeMemInit(v725, v2, 1);
      v7 = v829;
      *(_QWORD *)(v724 + 8) = *((_QWORD *)v6 + 2);
      *(_BYTE *)(v724 + 42) = v723;
      *(_DWORD *)(v724 + 32) = -1431655765 * ((__int64)&v6[-v828] >> 3);
      v9 = v825;
      *(_QWORD *)(v724 + 24) = v4;
      *(_BYTE *)(v724 + 41) = 0;
      *(_DWORD *)(v724 + 36) = 0;
      LODWORD(v10) = 1;
      *(_BYTE *)(v724 + 40) = v825;
      *(_WORD *)v6 = -3677;
      *((_QWORD *)v6 + 2) = v724;
    }
    v726 = (_DWORD *)*((_QWORD *)v6 + 2);
    v727 = v7 + 56LL * *((int *)v6 + 3);
    if ( *((_QWORD *)v726 + 2) != v727 )
    {
      v728 = *((unsigned __int8 *)v726 + 42);
      *((_QWORD *)v726 + 2) = v727;
      while ( 1 )
      {
        v728 -= v10;
        if ( v728 < 0 )
          break;
        *(_QWORD *)&v726[2 * v728 + 12] = v7 + 56LL * (v728 + *((_DWORD *)v6 + 2));
      }
    }
    *(_DWORD *)(v727 + 16) += v10;
    v737 = v726 + 12;
    v738 = *((_QWORD *)v726 + 1);
    v739 = *((unsigned __int8 *)v726 + 42);
    if ( *((_DWORD *)v6 + 1) )
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v738 + 48))(v726, v739, v737);
    else
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v738 + 24))(v726, v739, v737);
    v740 = v726[9];
    v3 = 0;
    if ( !v740 )
      goto LABEL_1408;
    if ( v740 > 0 )
    {
      v741 = (const char *)sqlite3_value_text(*(_QWORD *)v726);
      sqlite3VdbeError(v4, "%s", v741);
      v14 = v726[9];
      Table = v14;
    }
    if ( *((_BYTE *)v726 + 41) )
    {
      if ( *((_DWORD *)v6 - 5) )
        sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 - 5), 1);
      *((_BYTE *)v726 + 41) = 0;
    }
    sqlite3VdbeMemRelease(*(_QWORD *)v726);
    v3 = 0;
    v10 = 1;
    *(_WORD *)(*(_QWORD *)v726 + 20LL) = 1;
    v726[9] = 0;
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
                                v9 = v825;
                                *(_DWORD *)(v20 + 16) = sqlite3Strlen30(v28);
                                *(_BYTE *)(v20 + 22) = 1;
                                sqlite3VdbeChangeEncoding(v20, v825);
                                v4 = a1;
LABEL_50:
                                v3 = 0;
                                if ( v14 )
                                  goto LABEL_1546;
LABEL_51:
                                v7 = v829;
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
                        v808 = "into";
                        v14 = 1;
                        v809 = "cannot change %s wal mode from within a transaction";
                        if ( v21 != 5 )
                          v808 = "out of";
LABEL_1538:
                        sqlite3VdbeError(v4, v809, v808);
                        goto LABEL_1523;
                      }
                      v29 = *((_DWORD *)v6 + 2);
                      v30 = *((_DWORD *)v6 + 1);
                      v862 = 0;
                      v863 = -1;
                      v31 = sqlite3Checkpoint(v2, v30, v29, (unsigned int)&v863, (__int64)&v863 + 4);
                      v3 = 0;
                      Table = v31;
                      v14 = v31;
                      if ( v31 )
                      {
                        if ( v31 != 5 )
                          goto LABEL_1546;
                        v14 = 0;
                        Table = 0;
                        v862 = 1;
                      }
                      v32 = 0;
                      v33 = v7 + 56LL * *((int *)v6 + 3);
                      do
                      {
                        sqlite3VdbeMemSetInt64(v33, *(&v862 + v32));
                        v10 = 1;
                        v33 += 56;
                        ++v32;
                      }
                      while ( v32 != 3 );
                      goto LABEL_59;
                    }
                    v34 = *((unsigned int *)v6 + 2);
                    LODWORD(v832) = 0;
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
                      v38 = sqlite3BtreeBeginTrans(*(_QWORD *)(v36 + v35 + 8), v34, &v832);
                      v3 = 0;
                      Table = v38;
                      v14 = v38;
                      if ( v38 )
                      {
                        if ( (_BYTE)v38 == 5 )
                        {
                          *((_DWORD *)v4 + 13) = v38;
                          *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v828] >> 3);
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
                          && ((_DWORD)v832 != *((_DWORD *)v6 + 3)
                           || *(_DWORD *)(*(_QWORD *)(v36 + v35 + 24) + 4LL) != *((_DWORD *)v6 + 4)) )
                        {
                          if ( v4[21] )
                            sqlite3DbFreeNN(v2);
                          v4[21] = sqlite3DbStrDup(v2, "database schema has changed");
                          if ( **(_DWORD **)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 24) != (_DWORD)v832 )
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
                  v810 = *((_DWORD *)v6 + 1);
                  v811 = *((_DWORD *)v6 + 2);
                  if ( v810 != *(unsigned __int8 *)(v2 + 101) )
                  {
                    if ( v811 )
                    {
                      sqlite3RollbackAll(v2, 516);
                      v812 = 1;
                    }
                    else
                    {
                      if ( v810 && *(int *)(v2 + 224) > 0 )
                      {
                        sqlite3VdbeError(v4, "cannot commit transaction - SQL statements in progress");
                        goto LABEL_1485;
                      }
                      v14 = sqlite3VdbeCheckFk(v4, (unsigned int)v10);
                      if ( v14 )
                        goto LABEL_1564;
                      v812 = v810;
                    }
                    *(_BYTE *)(v2 + 101) = v812;
                    if ( (unsigned int)sqlite3VdbeHalt(v4) == 5 )
                    {
                      v14 = 5;
                      *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v828] >> 3);
                      *(_BYTE *)(v2 + 101) = 1 - v810;
                      *((_DWORD *)v4 + 13) = 5;
                    }
                    else
                    {
                      sqlite3CloseSavepoints(v2);
                      v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
                    }
                    goto LABEL_1564;
                  }
                  if ( v810 )
                  {
                    v813 = "cannot rollback - no transaction is active";
                    if ( !v811 )
                      v813 = "cannot commit - no transaction is active";
                    sqlite3VdbeError(v4, v813);
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
                  v837 = v41;
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
                    LODWORD(v834) = m;
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
                        v831 = (unsigned int *)(v49 + 3);
                        if ( v49[3] || !*(_BYTE *)(v2 + 109) )
                        {
                          LODWORD(v832) = 0;
                        }
                        else
                        {
                          LODWORD(v832) = 1;
                          v53 = 1;
                          if ( v41 == 1 )
                          {
                            v54 = sqlite3VdbeCheckFk(a1, 1);
                            if ( !v54 )
                            {
                              *(_BYTE *)(v833 + 101) = 1;
                              v55 = sqlite3VdbeHalt(a1);
                              v56 = v833;
                              if ( v55 == 5 )
                              {
                                v4 = a1;
                                v14 = 5;
                                *((_DWORD *)a1 + 12) = -1431655765 * ((__int64)&v6[-v828] >> 3);
                                *(_BYTE *)(v56 + 101) = 0;
                                *((_DWORD *)a1 + 13) = 5;
                                goto LABEL_1565;
                              }
                              v57 = *((_DWORD *)a1 + 13);
                              v3 = 0;
                              Table = v57;
                              if ( v57 )
                                *(_BYTE *)(v833 + 101) = 0;
                              else
                                *(_BYTE *)(v833 + 109) = 0;
                              v58 = (int *)(v56 + 752);
                              v10 = 1;
                              goto LABEL_129;
                            }
                            v14 = v54;
                            v4 = a1;
LABEL_1564:
                            v56 = v833;
                            goto LABEL_1565;
                          }
                        }
                        v58 = (int *)(v2 + 752);
                        v59 = *v58;
                        if ( v41 == 2 )
                        {
                          v60 = v833;
                          v61 = 0;
                          v62 = *(_DWORD *)(v833 + 44) & 1;
                          if ( *(int *)(v833 + 40) > 0 )
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
                              v60 = v833;
                              v10 = 1;
                              ++v61;
                            }
                            while ( v61 < *(_DWORD *)(v833 + 40) );
                            m = (unsigned int)v834;
                          }
                        }
                        else
                        {
                          v62 = 0;
                        }
                        v56 = v833;
                        m = v59 + ~m;
                        v64 = 0;
                        if ( *(int *)(v833 + 40) > 0 )
                        {
                          v65 = v837;
                          while ( 1 )
                          {
                            v57 = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v64 + *(_QWORD *)(v56 + 32) + 8), v65, m);
                            v3 = 0;
                            Table = v57;
                            if ( v57 )
                              goto LABEL_1544;
                            v56 = v833;
                            v10 = 1;
                            if ( ++v64 >= *(_DWORD *)(v833 + 40) )
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
                          v56 = v833;
                          v10 = 1;
                          v57 = Table;
                          *(_DWORD *)(v833 + 44) |= 1u;
                          v3 = 0;
                        }
                        v52 = v831;
                        v53 = v832;
                        v41 = v837;
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
                              v56 = v833;
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
                              v68 = v833;
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
                            v7 = v829;
LABEL_146:
                            v5 = v828;
LABEL_147:
                            v13 = v826;
LABEL_148:
                            v9 = v825;
LABEL_53:
                            v2 = v833;
                            v6 += 24;
                            v8 = v846;
                            goto LABEL_9;
                          }
                          v68 = v833;
                          *(_QWORD *)(v833 + 760) = v49[1];
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
                        v817 = v833;
                        if ( *(_BYTE *)(v833 + 103) == (_BYTE)v3 )
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
                          v818 = (const char *)sqlite3ErrStr(v14);
                          sqlite3VdbeError(v4, "%s", v818);
                        }
                        *((_DWORD *)v4 + 13) = v14;
                        sqlite3SystemError(v817, v14);
                        sqlite3_log(
                          v14,
                          "statement aborts at %d: [%s] %s",
                          -1431655765 * ((__int64)&v6[-v828] >> 3),
                          (const char *)v4[31],
                          (const char *)v4[21]);
                        if ( *((_BYTE *)v4 + 199) == 2 )
                          sqlite3VdbeHalt(v4);
                        if ( v14 == 3082 )
                        {
                          sqlite3OomFault(v817);
                          goto LABEL_1557;
                        }
                        if ( v14 == 11 )
                        {
                          v56 = v817;
                          if ( !*(_BYTE *)(v817 + 101) )
                            *(_QWORD *)(v817 + 48) |= 0x200000000uLL;
                        }
                        else
                        {
LABEL_1557:
                          v56 = v817;
                        }
                        v14 = 1;
                        if ( v836 )
                        {
                          sqlite3ResetOneSchema(v56);
                          v56 = v817;
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
                v795 = *(_BYTE *)(v2 + 110);
                if ( (v795 & 0x41) != 0 && *((_BYTE *)v4 + 197) != 0xFE )
                {
                  v796 = (const char *)*((_QWORD *)v6 + 2);
                  if ( v796 || (v796 = (const char *)v4[31]) != 0 )
                  {
                    if ( (v795 & 0x40) != 0 )
                    {
                      v797 = sqlite3VdbeExpandSql(v4, v796);
                      (*(void (__fastcall **)(_QWORD, __int64))(v2 + 248))(*(_QWORD *)(v2 + 256), v797);
                      sqlite3_free(v797);
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
                      v798 = sqlite3MPrintf(v2, "-- %s", v796);
                      (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v2 + 248))(
                        1,
                        *(_QWORD *)(v2 + 256),
                        v4,
                        v798);
                      sqlite3DbFree(v2, v798);
                    }
                    v5 = v828;
                    v3 = 0;
                    v13 = v826;
                    v10 = 1;
                  }
                }
                v799 = *((_DWORD *)v6 + 1);
                if ( v799 >= dword_180159488 )
                {
                  if ( *v6 == 0xB8 )
                    goto LABEL_53;
                  for ( ii = v10; ii < *((_DWORD *)v4 + 36); ii += v10 )
                  {
                    v801 = v4[17];
                    if ( *(_BYTE *)(v801 + 24LL * ii) == 15 )
                      *(_DWORD *)(v801 + 24LL * ii + 4) = 0;
                  }
                  v799 = 0;
                }
                *((_DWORD *)v6 + 1) = v799 + 1;
                *((_DWORD *)v4 + 59) += v10;
                goto LABEL_215;
              }
              v831 = 0;
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
                      v7 = v829;
                    }
                    *(_BYTE *)(v2 + 108) = v6[2];
                    Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int **))(v3 + 104))(
                              v78,
                              v80,
                              v82,
                              &v831);
                    *(_BYTE *)(v2 + 108) = v81;
                    v14 = Table;
                    sqlite3VtabImportErrmsg(v4, v78);
                    v3 = 0;
                    if ( !Table )
                    {
                      if ( *((_DWORD *)v6 + 1) )
                        *(_QWORD *)(v2 + 56) = v831;
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
            v92 = *(unsigned int *)(v86 + v829);
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
                    v13 = v826;
                    *(_BYTE *)(v108 + v107) = v111;
LABEL_201:
                    *((_DWORD *)v6 + 1) = *(_DWORD *)(v4[17] + 4);
LABEL_202:
                    v5 = v828;
                    goto LABEL_53;
                  }
                }
                else if ( *(_DWORD *)(v4[17] + 4) != *((_DWORD *)v6 + 1) )
                {
                  goto LABEL_201;
                }
LABEL_214:
                v5 = v828;
LABEL_215:
                v4 = a1;
                v7 = v829;
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
              v5 = v828;
              v10 = 1;
              v13 = v826;
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
            *(_QWORD *)&v840 = 0;
            v121 = v4[15];
            v122 = 0;
            LODWORD(v834) = 0;
            v838 = 0;
            v839 = 0;
            v123 = *(_QWORD *)(v121 + 8 * v120);
            *(_WORD *)(v123 + 2) = 0;
            *(_DWORD *)(v123 + 32) = 0;
            if ( *(_BYTE *)(v123 + 4) )
            {
              v124 = v829 + 56LL * *((int *)v6 + 3);
              v125 = *(_WORD *)(v124 + 20);
              if ( (v125 & 0x2E) == 2 )
                applyNumericAffinity(v124, 0);
              v126 = sqlite3VdbeIntValue(v124, v13);
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
                  v149 = btreeLast(v129, &v834);
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
              v152 = sqlite3BtreeTableMoveto(*(_QWORD *)(v123 + 48), v128, 0, &v834);
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
              *(_QWORD *)&v838 = *(_QWORD *)(v123 + 56);
              LOBYTE(v122) = v153 != 0;
              WORD6(v839) = *((_WORD *)v6 + 8);
              BYTE2(v840) = 0;
              v154 = *((int *)v6 + 3);
              BYTE14(v839) = v10 + (((unsigned __int8)v10 & (unsigned __int8)(v15 - 1)) != 0 ? 0xFE : 0);
              *((_QWORD *)&v838 + 1) = v829 + 56 * v154;
              v155 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v123 + 48), &v838, &v834);
              v3 = 0;
              Table = v155;
              v14 = v155;
              if ( v155 )
                goto LABEL_1545;
              if ( v153 )
              {
                if ( !BYTE2(v840) )
                  goto LABEL_277;
              }
              else
              {
                v122 = 0;
              }
            }
            if ( (int)v15 < 23 )
            {
              if ( (int)v834 <= 0 && ((_DWORD)v834 || (_DWORD)v15 != 21) )
              {
                v130 = *(_BYTE *)*v151 != 0;
                goto LABEL_278;
              }
              LODWORD(v834) = 0;
              v156 = sqlite3BtreePrevious(*v151, 0);
            }
            else
            {
              if ( (int)v834 >= 0 && ((_DWORD)v834 || (_DWORD)v15 != 24) )
              {
LABEL_279:
                v4 = a1;
                v7 = v829;
                v13 = v826;
                v10 = 1;
                if ( v122 )
                  v6 += 24;
                goto LABEL_623;
              }
              LODWORD(v834) = 0;
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
            v130 = (int)v834;
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
            v5 = v828;
            v13 = v826;
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
          LOBYTE(v141) = *((_BYTE *)qword_1801400C0 + (*(_WORD *)(56LL * *((int *)v6 + 3) + v7 + 20) & 0x3F));
        }
        else
        {
          v138 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( *((_DWORD *)v6 + 3) < (int)*(unsigned __int16 *)(v138 + 74) )
          {
            v139 = *(unsigned int *)(v138 + 4LL * *((int *)v6 + 3) + 120);
            if ( (unsigned int)v139 < 0xC )
              v140 = *((unsigned __int8 *)&qword_180140910[1] + v139);
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
              *(_QWORD *)&v840 = 0;
              v144 = v4[15];
              v838 = 0;
              v839 = 0;
              v145 = *(_QWORD *)(v144 + 8 * v143);
              v146 = v7 + 56LL * *((int *)v6 + 3);
              WORD6(v839) = *((_WORD *)v6 + 8);
              *((_QWORD *)&v838 + 1) = v146;
              if ( WORD6(v839) )
              {
                v147 = (int *)(v145 + 36);
                *(_QWORD *)&v838 = *(_QWORD *)(v145 + 56);
                BYTE14(v839) = 0;
                v14 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v145 + 48), &v838, v145 + 36);
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
                  *(unsigned int *)(*((_QWORD *)&v838 + 1) + 16LL),
                  *(_QWORD *)(*((_QWORD *)&v838 + 1) + 8LL),
                  v171);
                *(_BYTE *)(v172 + 30) = 0;
                v147 = (int *)(v145 + 36);
                Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v145 + 48), v172, v145 + 36);
                v14 = Table;
                sqlite3DbFreeNN(v2);
                v9 = v825;
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
                v7 = v829;
                goto LABEL_195;
              }
              if ( v173 )
                goto LABEL_1218;
              v10 = 1;
              if ( *v6 == 27 )
              {
                v174 = 0;
                if ( !WORD6(v839) )
                  goto LABEL_1403;
                while ( (*(_BYTE *)(56LL * v174 + *((_QWORD *)&v838 + 1) + 20) & 1) == 0 )
                {
                  if ( (int)++v174 >= WORD6(v839) )
                    goto LABEL_335;
                }
                goto LABEL_1219;
              }
              v7 = v829;
              v13 = v826;
              if ( *v6 == 26 )
              {
                *(_WORD *)(v145 + 12) = *((_WORD *)v6 + 8);
                goto LABEL_1078;
              }
LABEL_623:
              v5 = v828;
LABEL_978:
              v9 = v825;
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
              v843 = 0;
              if ( (*(_BYTE *)(v163 + v7 + 20) & 0x24) == 0 )
              {
                LOBYTE(v5) = v9;
                LOBYTE(v13) = 67;
                v164 = *(_OWORD *)(v163 + v7 + 16);
                v847 = *(_OWORD *)(v163 + v7);
                v165 = *(_OWORD *)(v163 + v7 + 32);
                v848 = v164;
                *(_QWORD *)&v164 = *(_QWORD *)(v163 + v7 + 48);
                v849 = v165;
                v850 = v164;
                applyAffinity(&v847, v13, v5);
                v3 = 0;
                if ( (BYTE4(v848) & 4) == 0 )
                  goto LABEL_1218;
                v166 = v847;
                goto LABEL_322;
              }
              break;
            case 0x1F:
              break;
            case 0x20:
LABEL_1211:
              v638 = *((int *)v6 + 1);
              v639 = v4[15];
              LODWORD(v832) = 0;
              v640 = *(_QWORD *)(v639 + 8 * v638);
              v641 = *(_QWORD *)(v640 + 48);
              if ( (_BYTE)v15 == 0x89 )
              {
                v642 = *(_QWORD *)(v640 + 48);
                *(_DWORD *)(v640 + 36) = -1;
                IsValidNN = sqlite3BtreeCursorIsValidNN(v642);
                v3 = 0;
                if ( IsValidNN )
                  goto LABEL_1407;
              }
              v644 = sqlite3BtreeLast(v641, &v832);
              v3 = 0;
              Table = v644;
              v14 = v644;
              *(_BYTE *)(v640 + 2) = v832;
              *(_BYTE *)(v640 + 3) = 0;
              *(_DWORD *)(v640 + 32) = 0;
              if ( v644 )
                goto LABEL_1546;
              if ( *((int *)v6 + 2) <= 0 )
                goto LABEL_1407;
              if ( (_DWORD)v832 )
                goto LABEL_1218;
              goto LABEL_79;
            default:
              v157 = *((int *)v6 + 1);
              v158 = v4[15];
              LODWORD(v832) = 0;
              v159 = *(_QWORD *)(*(_QWORD *)(v158 + 8 * v157) + 48LL);
              v160 = sqlite3BtreeFirst(v159, &v832);
              v3 = 0;
              Table = v160;
              v14 = v160;
              if ( v160 )
                goto LABEL_1546;
              if ( (_DWORD)v832 )
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
          v843 = 0;
          v169 = sqlite3BtreeTableMoveto(v168, v166, 0, &v843);
          v3 = 0;
          *(_QWORD *)(v167 + 80) = v166;
          *(_WORD *)(v167 + 2) = 0;
          v14 = v169;
          *(_DWORD *)(v167 + 32) = 0;
          Table = v169;
          *(_DWORD *)(v167 + 36) = v843;
          if ( v843 )
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
          v188 = &qword_18013C180;
          if ( *v6 != 44 )
            v188 = qword_18013D2D0;
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
          LODWORD(v834) = 0;
          v183 = *(_QWORD *)(v182 + 8 * v181);
          LODWORD(v834) = v10;
          if ( *(_BYTE *)v183 == (_BYTE)v10 )
          {
            v184 = sqlite3VdbeSorterRewind(v183, &v834);
            v3 = 0;
          }
          else
          {
            v184 = sqlite3BtreeFirst(*(_QWORD *)(v183 + 48), &v834);
            v3 = 0;
            *(_BYTE *)(v183 + 3) = 0;
            *(_DWORD *)(v183 + 32) = 0;
          }
          Table = v184;
          v14 = v184;
          if ( v184 )
            goto LABEL_1546;
          *(_BYTE *)(v183 + 2) = (_BYTE)v834;
          if ( *((int *)v6 + 2) <= 0 )
            goto LABEL_1408;
          v105 = (_DWORD)v834 == 0;
LABEL_194:
          v10 = 1;
          if ( v105 )
          {
LABEL_195:
            v5 = v828;
            goto LABEL_196;
          }
LABEL_1219:
          v9 = v825;
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
          v5 = v828;
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
        v716 = v845;
        if ( v846 >= v845 )
        {
          while ( 1 )
          {
            v717 = *(__int64 (__fastcall **)(_QWORD))(v2 + 528);
            if ( !v717 )
              goto LABEL_1407;
            v718 = *(unsigned int *)(v2 + 544);
            v719 = v717(*(_QWORD *)(v2 + 536));
            v3 = 0;
            if ( v719 )
              goto LABEL_1535;
            v716 += v718;
            v845 = v716;
            if ( v846 < v716 )
              goto LABEL_51;
          }
        }
LABEL_1403:
        v7 = v829;
LABEL_1404:
        v13 = v826;
        goto LABEL_623;
      }
    }
    v193 = *((int *)v6 + 1);
    *(_QWORD *)&v840 = 0;
    v194 = v4[15];
    v838 = 0;
    v839 = 0;
    v195 = *(_QWORD *)(v194 + 8 * v193);
    v847 = 0;
    v848 = 0;
    *(_QWORD *)&v838 = *(_QWORD *)(v195 + 56);
    WORD6(v839) = *((_WORD *)v6 + 8);
    BYTE14(v839) = -((unsigned __int8)v15 < 0x2Au);
    v196 = 56LL * *((int *)v6 + 3);
    v849 = 0;
    v850 = 0;
    *((_QWORD *)&v838 + 1) = v7 + v196;
    v197 = *(_QWORD *)(v195 + 48);
    v198 = sqlite3BtreePayloadSize(v197);
    if ( v198 - 1 <= 0x7FFFFFFE )
    {
      sqlite3VdbeMemInit(&v847, v2, 0);
      v199 = sqlite3VdbeMemFromBtreeZeroOffset(v197, v198, &v847);
      v3 = 0;
      Table = v199;
      v14 = v199;
      if ( v199 )
        goto LABEL_1546;
      v200 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v848, *((_QWORD *)&v847 + 1), &v838, 0);
      sqlite3VdbeMemReleaseMalloc(&v847);
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
    v814 = sqlite3CorruptError(100143);
LABEL_1530:
    v14 = v814;
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
          v5 = v828;
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
          *(_BYTE *)(v266 + 40) = v825;
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
      v9 = v825;
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
            v831 = (unsigned int *)v209;
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
              v829 = v216 + 112;
              *(_QWORD *)(v216 + 56) = *(_QWORD *)(v833 + 56);
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
              v2 = v833;
              v6 = (unsigned __int8 *)(v223 - 24);
              v828 = v223;
              *((_DWORD *)v4 + 36) = v224;
LABEL_1308:
              v3 = 0;
              goto LABEL_1309;
            }
            v214 = *v211 + *(_DWORD *)(v209 + 12) + 1;
            if ( *v211 )
              v214 = *v211 + *(_DWORD *)(v209 + 12);
            v215 = (*v212 + 7) / 8 + 8 * (*v211 + 7 * (v214 + 2));
            v216 = sqlite3DbMallocZero(v833, v215);
            if ( v216 )
            {
              sqlite3VdbeMemRelease(v213);
              *(_QWORD *)(v213 + 48) = sqlite3VdbeFrameMemDel;
              v217 = v216 + 112;
              *(_DWORD *)(v213 + 16) = v215;
              v4 = a1;
              *(_WORD *)(v213 + 20) = 4112;
              *(_QWORD *)(v213 + 8) = v216;
              v218 = (__int64 *)v831;
              *(_QWORD *)v216 = a1;
              *(_DWORD *)(v216 + 88) = v214;
              *(_DWORD *)(v216 + 92) = *v211;
              *(_DWORD *)(v216 + 76) = -1431655765 * ((__int64)&v6[-v828] >> 3);
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
                v220 = v833;
                do
                {
                  *(_WORD *)(v217 + 20) = 0;
                  *(_QWORD *)(v217 + 24) = v220;
                  v217 += 56;
                }
                while ( v217 != v219 );
                v4 = a1;
              }
              v9 = v825;
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
            v231 = sqlite3RowSetTest(*(_QWORD *)(v226 + 8), (unsigned int)v225, *(_QWORD *)(v229 + v829));
            v3 = 0;
            if ( v231 )
              goto LABEL_1218;
            v230 = v225 < 0;
          }
          if ( v230 )
          {
LABEL_79:
            v7 = v829;
            goto LABEL_80;
          }
          sqlite3RowSetInsert(*(_QWORD *)(v226 + 8), *(_QWORD *)(v229 + v829));
LABEL_421:
          v7 = v829;
          goto LABEL_422;
        }
        v232 = *((int *)v6 + 1);
        v831 = 0;
        v233 = v7 + 56 * v232;
        if ( (*(_BYTE *)(v233 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v233 + 8), &v831) )
        {
          sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 + 3), v831);
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
        v9 = v825;
        if ( *(_QWORD *)v235 >= *(_QWORD *)v234 )
        {
          if ( *((_BYTE *)&qword_18013D740[26] + v239 + 2) )
            goto LABEL_215;
          v13 = 0;
        }
        else
        {
          if ( *((_BYTE *)&qword_18013D740[25] + v239 + 4) )
            goto LABEL_215;
          v13 = 0xFFFFFFFFLL;
        }
        goto LABEL_438;
      }
      v238 = *((_BYTE *)&qword_18013D740[27] + v15) == 0;
LABEL_436:
      v9 = v825;
      if ( !v238 )
        goto LABEL_215;
      v13 = (unsigned int)v10;
LABEL_438:
      v4 = a1;
      v7 = v829;
      v826 = v13;
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
        v826 = v13;
LABEL_450:
        v241 = *v6;
        if ( (_DWORD)v13 )
          v242 = *((_BYTE *)&qword_18013D740[27] + v241);
        else
          v242 = *((_BYTE *)&qword_18013D740[26] + v241 + 2);
LABEL_476:
        *(_WORD *)(v235 + 20) = v237;
        *(_WORD *)(v234 + 20) = v236;
        if ( !v242 )
        {
          v4 = a1;
          v7 = v829;
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
      v826 = -1;
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
            LOBYTE(v13) = v825;
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
            LOBYTE(v13) = v825;
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
      v5 = v828;
      v3 = 0;
      v826 = v244;
      v13 = (unsigned int)v244;
      v10 = 1;
      if ( v244 >= 0 )
        goto LABEL_450;
    }
    v242 = *((_BYTE *)&qword_18013D740[25] + *v6 + 4);
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
          v831 = v330;
          LODWORD(v832) = v328;
          v837 = v331;
          LODWORD(v834) = v332;
          if ( v328 <= 0 )
            goto LABEL_616;
          while ( 1 )
          {
            v333 = v327 ? *(_DWORD *)(v327 + 4LL * v329) : v329;
            v334 = v829 + 56LL * (unsigned int)(v333 + v332);
            v335 = (unsigned __int8)(v10 & *(_BYTE *)(*((_QWORD *)v330 + 3) + v329));
            v336 = v829 + 56LL * (v333 + v331);
            v337 = sqlite3MemCompare(v336, v334, *(_QWORD *)&v330[2 * v329 + 8]);
            v3 = 0;
            v826 = v337;
            v13 = v337;
            v10 = 1;
            if ( v337 )
              break;
            v330 = v831;
            ++v329;
            v331 = v837;
            v332 = (int)v834;
            if ( (int)v329 >= (int)v832 )
            {
              v14 = Table;
              v4 = a1;
LABEL_616:
              v7 = v829;
              v5 = v828;
              goto LABEL_148;
            }
          }
          if ( (*(_BYTE *)(v329 + *((_QWORD *)v831 + 3)) & 2) != 0
            && ((*(_BYTE *)(v336 + 20) & 1) != 0 || (*(_BYTE *)(v334 + 20) & 1) != 0) )
          {
            v13 = -v337;
            v826 = -v337;
          }
          v14 = Table;
          v4 = a1;
          v7 = v829;
          if ( v335 )
          {
            v13 = (unsigned int)-(int)v13;
            v826 = v13;
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
                v5 = v828;
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
      v5 = v828;
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
    v310 = v829 + 56LL * *((int *)v6 + 1);
    for ( kk = v829 + 56LL * *((int *)v6 + 2); ; kk += 56 )
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
          v294 = v829 + 56LL * *((int *)v6 + 1);
          v295 = v829 + 56LL * *((int *)v6 + 2);
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
    v828 = v5;
    v829 = v7;
    v6 = (unsigned __int8 *)(v5 + 24LL * v288);
    goto LABEL_61;
  }
  v815 = *((_DWORD *)v6 + 1);
  *((_DWORD *)v4 + 13) = v815;
  *((_BYTE *)v4 + 196) = v6[8];
  if ( v815 )
  {
    if ( *((_WORD *)v6 + 1) )
    {
      sqlite3VdbeError(v4, "%s constraint failed", off_18010AF50[*((unsigned __int16 *)v6 + 1)]);
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
      -1431655765 * ((__int64)&v6[-v828] >> 3),
      (const char *)v4[31],
      (const char *)v4[21]);
  }
  v816 = sqlite3VdbeHalt(v4);
  v56 = v833;
  v14 = v816;
  if ( v816 == 5 )
    *((_DWORD *)v4 + 13) = 5;
  else
    v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
LABEL_1565:
  while ( 1 )
  {
    v819 = v845;
    if ( v846 < v845 )
      break;
    v820 = *(__int64 (__fastcall **)(__int64))(v56 + 528);
    if ( !v820 )
      break;
    v821 = *(_QWORD *)(v56 + 536);
    v845 += *(unsigned int *)(v56 + 544);
    v822 = v820(v821);
    v56 = v833;
    v3 = 0;
    if ( v822 )
    {
LABEL_1535:
      v845 = -1;
      goto LABEL_1536;
    }
  }
  *((_DWORD *)v4 + 57) += v846;
  if ( *((_DWORD *)v4 + 52) )
    sqlite3VdbeLeave(v4, v819, v56);
  return v14;
}

```

## disassembly

```asm
0x1800ade30  mov     rax, rsp
0x1800ade33  push    rbp
0x1800ade34  push    rbx
0x1800ade35  push    rsi
0x1800ade36  push    rdi
0x1800ade37  push    r12
0x1800ade39  push    r13
0x1800ade3b  push    r14
0x1800ade3d  push    r15
0x1800ade3f  lea     rbp, [rax-178h]
0x1800ade46  sub     rsp, 238h
0x1800ade4d  movaps  xmmword ptr [rax-58h], xmm6
0x1800ade51  movaps  xmmword ptr [rax-68h], xmm7
0x1800ade55  mov     rax, cs:__security_cookie
0x1800ade5c  xor     rax, rsp
0x1800ade5f  mov     [rbp+170h+var_70], rax
0x1800ade66  mov     r13, [rcx]
0x1800ade69  xor     r10d, r10d
0x1800ade6c  mov     r15, rcx
0x1800ade6f  mov     r8, [rcx+88h]
0x1800ade76  mov     r14, r8
0x1800ade79  mov     rsi, [rcx+68h]
0x1800ade7d  mov     r9d, r10d
0x1800ade80  mov     [rsp+270h+var_210], rcx
0x1800ade85  mov     dil, [r13+64h]
0x1800ade89  mov     byte ptr [rsp+270h+var_230], dil
0x1800ade8e  mov     [rsp+270h+var_220], r8
0x1800ade93  mov     [rsp+270h+var_1F8], r13
0x1800ade98  mov     [rbp+170h+var_1E4], r10b
0x1800ade9c  mov     [rbp+170h+var_180], r10
0x1800adea0  mov     [rsp+270h+var_218], rsi
0x1800adea5  cmp     [rcx+0D0h], r10d
0x1800adeac  jz      short loc_1800ADEBD
0x1800adeae  call    sqlite3VdbeEnter
0x1800adeb3  mov     r9, [rbp+170h+var_180]
0x1800adeb7  mov     r8, r14
0x1800adeba  xor     r10d, r10d
0x1800adebd  cmp     [r13+210h], r10
0x1800adec4  jz      short loc_1800ADEE2
0x1800adec6  mov     eax, [r15+0E4h]
0x1800adecd  xor     edx, edx
0x1800adecf  mov     ecx, [r13+220h]
0x1800aded6  div     ecx
0x1800aded8  sub     ecx, edx
0x1800adeda  mov     eax, ecx
0x1800adedc  mov     [rbp+170h+var_188], rax
0x1800adee0  jmp     short loc_1800ADEEA
0x1800adee2  mov     [rbp+170h+var_188], 0FFFFFFFFFFFFFFFFh
0x1800adeea  cmp     dword ptr [r15+34h], 7
0x1800adeef  mov     r11d, 1
0x1800adef5  jz      loc_1800B4221
0x1800adefb  mov     [r15+34h], r10d
0x1800adeff  mov     [r15+48h], r10
0x1800adf03  mov     eax, [r13+198h]
0x1800adf0a  mov     [r13+298h], r10d
0x1800adf11  test    eax, eax
0x1800adf13  jnz     loc_1800B41D9
0x1800adf19  movsxd  rax, dword ptr [r15+30h]
0x1800adf1d  mov     edx, r10d
0x1800adf20  mov     r12d, r10d
0x1800adf23  mov     dword ptr [rsp+270h+var_228], r10d
0x1800adf28  mov     [rsp+270h+var_22C], edx
0x1800adf2c  xorps   xmm7, xmm7
0x1800adf2f  mov     [rbp+170h+var_1A8], r10d
0x1800adf33  lea     rcx, [rax+rax*2]
0x1800adf37  lea     r14, [r8+rcx*8]
0x1800adf3b  lea     ecx, [r11+3]
0x1800adf3f  movzx   ebx, byte ptr [r14]
0x1800adf43  add     r9, r11
0x1800adf46  mov     [rbp+170h+var_1A0], r14
0x1800adf4a  mov     eax, 5
0x1800adf4f  mov     [rbp+170h+var_180], r9
0x1800adf53  cmp     ebx, 5Ch ; '\'
0x1800adf56  ja      loc_1800B05D8
0x1800adf5c  jz      loc_1800B0589
0x1800adf62  cmp     ebx, 2Dh ; '-'
0x1800adf65  ja      loc_1800AF5EE
0x1800adf6b  jz      loc_1800AF50D
0x1800adf71  cmp     ebx, 16h
0x1800adf74  ja      loc_1800AEDE2
0x1800adf7a  jz      loc_1800AEBC5
0x1800adf80  cmp     ebx, 0Bh
0x1800adf83  ja      loc_1800AE998
0x1800adf89  jz      loc_1800AE96D
0x1800adf8f  cmp     ebx, eax
0x1800adf91  ja      loc_1800AE75D
0x1800adf97  jz      loc_1800AE71D
0x1800adf9d  test    ebx, ebx
0x1800adf9f  jz      loc_1800AE32F
0x1800adfa5  sub     ebx, 1
0x1800adfa8  jz      loc_1800B3E01
0x1800adfae  sub     ebx, 1
0x1800adfb1  jz      loc_1800AE202
0x1800adfb7  sub     ebx, 1
0x1800adfba  jz      loc_1800AE15A
0x1800adfc0  cmp     ebx, 1
0x1800adfc3  jnz     loc_1800AE148
0x1800adfc9  mov     rdx, r14
0x1800adfcc  mov     rcx, r15
0x1800adfcf  call    out2Prerelease
0x1800adfd4  movsxd  rcx, dword ptr [r14+4]
0x1800adfd8  mov     r15, rax
0x1800adfdb  mov     rax, [r13+20h]
0x1800adfdf  mov     ebx, [r14+0Ch]
0x1800adfe3  shl     rcx, 5
0x1800adfe7  mov     r12, [rcx+rax+8]
0x1800adfec  mov     rcx, r12
0x1800adfef  call    sqlite3BtreePager
0x1800adff4  mov     rcx, rax
0x1800adff7  mov     rsi, rax
0x1800adffa  call    sqlite3PagerGetJournalMode
0x1800adfff  cmp     ebx, 0FFFFFFFFh
0x1800ae002  mov     rcx, rsi
0x1800ae005  mov     edi, eax
0x1800ae007  cmovz   ebx, eax
0x1800ae00a  call    sqlite3PagerOkToChangeJournalMode
0x1800ae00f  test    eax, eax
0x1800ae011  mov     edx, 1
0x1800ae016  mov     rcx, rsi
0x1800ae019  cmovz   ebx, edi
0x1800ae01c  call    sqlite3PagerFilename
0x1800ae021  mov     ecx, 5
0x1800ae026  cmp     ebx, ecx
0x1800ae028  jnz     short loc_1800AE05C
0x1800ae02a  mov     rcx, rax
0x1800ae02d  call    sqlite3Strlen30
0x1800ae032  test    eax, eax
0x1800ae034  jz      short loc_1800AE042
0x1800ae036  mov     rcx, rsi
0x1800ae039  call    sqlite3PagerWalSupported
0x1800ae03e  test    eax, eax
0x1800ae040  jnz     short loc_1800AE057
0x1800ae042  mov     ebx, edi
0x1800ae044  mov     r12d, dword ptr [rsp+270h+var_228]
0x1800ae049  test    r12d, r12d
0x1800ae04c  jz      loc_1800AE0E2
0x1800ae052  jmp     loc_1800AE0E0
0x1800ae057  mov     ecx, 5
0x1800ae05c  cmp     ebx, edi
0x1800ae05e  jz      short loc_1800AE044
0x1800ae060  cmp     edi, ecx
0x1800ae062  jz      short loc_1800AE068
0x1800ae064  cmp     ebx, ecx
0x1800ae066  jnz     short loc_1800AE044
0x1800ae068  cmp     byte ptr [r13+65h], 0
0x1800ae06d  jz      loc_1800B3D20
0x1800ae073  cmp     dword ptr [r13+0DCh], 1
0x1800ae07b  jg      loc_1800B3D20
0x1800ae081  cmp     edi, ecx
0x1800ae083  jnz     short loc_1800AE0A4
0x1800ae085  mov     rdx, r13
0x1800ae088  mov     rcx, rsi
0x1800ae08b  call    sqlite3PagerCloseWal
0x1800ae090  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae094  test    eax, eax
0x1800ae096  jnz     short loc_1800AE0DB
0x1800ae098  mov     edx, ebx
0x1800ae09a  mov     rcx, rsi
0x1800ae09d  call    sqlite3PagerSetJournalMode
0x1800ae0a2  jmp     short loc_1800AE0BB
0x1800ae0a4  cmp     edi, 4
0x1800ae0a7  jnz     short loc_1800AE0B4
0x1800ae0a9  lea     edx, [rdi-2]
0x1800ae0ac  mov     rcx, rsi
0x1800ae0af  call    sqlite3PagerSetJournalMode
0x1800ae0b4  cmp     dword ptr [rsp+270h+var_228], 0
0x1800ae0b9  jnz     short loc_1800AE0DB
0x1800ae0bb  xor     edx, edx
0x1800ae0bd  lea     ecx, [rdx+5]
0x1800ae0c0  cmp     ebx, ecx
0x1800ae0c2  mov     rcx, r12
0x1800ae0c5  setz    dl
0x1800ae0c8  inc     edx
0x1800ae0ca  call    sqlite3BtreeSetVersion
0x1800ae0cf  mov     r12d, eax
0x1800ae0d2  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae0d6  jmp     loc_1800AE049
0x1800ae0db  mov     r12d, dword ptr [rsp+270h+var_228]
0x1800ae0e0  mov     ebx, edi
0x1800ae0e2  mov     edx, ebx
0x1800ae0e4  mov     rcx, rsi
0x1800ae0e7  call    sqlite3PagerSetJournalMode
0x1800ae0ec  mov     ecx, eax
0x1800ae0ee  mov     word ptr [r15+14h], 2202h
0x1800ae0f5  call    sqlite3JournalModename
0x1800ae0fa  mov     rcx, rax
0x1800ae0fd  mov     [r15+8], rax
0x1800ae101  call    sqlite3Strlen30
0x1800ae106  movzx   edi, byte ptr [rsp+270h+var_230]
0x1800ae10b  mov     rcx, r15
0x1800ae10e  mov     edx, edi
0x1800ae110  mov     [r15+10h], eax
0x1800ae114  mov     byte ptr [r15+16h], 1
0x1800ae119  call    sqlite3VdbeChangeEncoding
0x1800ae11e  mov     r15, [rsp+270h+var_210]
0x1800ae123  xor     r10d, r10d
0x1800ae126  test    r12d, r12d
0x1800ae129  jnz     loc_1800B424D
0x1800ae12f  mov     rsi, [rsp+270h+var_218]
0x1800ae134  mov     r8, [rsp+270h+var_220]
0x1800ae139  mov     r11d, 1
0x1800ae13f  mov     edx, [rsp+270h+var_22C]
0x1800ae143  mov     ecx, 4
0x1800ae148  mov     r13, [rsp+270h+var_1F8]
0x1800ae14d  add     r14, 18h
0x1800ae151  mov     r9, [rbp+170h+var_180]
0x1800ae155  jmp     loc_1800ADF3F
0x1800ae15a  mov     r8d, [r14+8]
0x1800ae15e  lea     rax, [rbp+170h+var_7C+4]
0x1800ae165  mov     edx, [r14+4]
0x1800ae169  lea     r9, [rbp+170h+var_7C]
0x1800ae170  mov     rcx, r13
0x1800ae173  mov     [rsp+270h+var_250], rax
0x1800ae178  mov     [rbp+170h+var_80], r10d
0x1800ae17f  mov     [rbp+170h+var_7C], 0FFFFFFFFFFFFFFFFh
0x1800ae18a  call    sqlite3Checkpoint
0x1800ae18f  xor     r10d, r10d
0x1800ae192  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae196  mov     r12d, eax
0x1800ae199  test    eax, eax
0x1800ae19b  jz      short loc_1800AE1BB
0x1800ae19d  lea     ecx, [r10+5]
0x1800ae1a1  cmp     eax, ecx
0x1800ae1a3  jnz     loc_1800B424D
0x1800ae1a9  mov     r12d, r10d
0x1800ae1ac  mov     dword ptr [rsp+270h+var_228], r10d
0x1800ae1b1  mov     [rbp+170h+var_80], 1
0x1800ae1bb  movsxd  rax, dword ptr [r14+0Ch]
0x1800ae1bf  mov     rdi, r10
0x1800ae1c2  imul    rbx, rax, 38h ; '8'
0x1800ae1c6  add     rbx, rsi
0x1800ae1c9  movsxd  rdx, [rbp+rdi*4+170h+var_80]
0x1800ae1d1  mov     rcx, rbx
0x1800ae1d4  call    sqlite3VdbeMemSetInt64
0x1800ae1d9  mov     r11d, 1
0x1800ae1df  add     rbx, 38h ; '8'
0x1800ae1e3  add     rdi, r11
0x1800ae1e6  cmp     rdi, 3
0x1800ae1ea  jnz     short loc_1800AE1C9
0x1800ae1ec  mov     dil, byte ptr [rsp+270h+var_230]
0x1800ae1f1  mov     r8, [rsp+270h+var_220]
0x1800ae1f6  mov     edx, [rsp+270h+var_22C]
0x1800ae1fa  xor     r10d, r10d
0x1800ae1fd  jmp     loc_1800AE143
0x1800ae202  mov     edx, [r14+8]
0x1800ae206  mov     dword ptr [rsp+270h+var_200], r10d
0x1800ae20b  test    edx, edx
0x1800ae20d  jz      short loc_1800AE226
0x1800ae20f  mov     rax, [r13+30h]
0x1800ae213  mov     rcx, 200100000h
0x1800ae21d  test    rcx, rax
0x1800ae220  jnz     loc_1800B3D4B
0x1800ae226  movsxd  rdi, dword ptr [r14+4]
0x1800ae22a  mov     rsi, [r13+20h]
0x1800ae22e  shl     rdi, 5
0x1800ae232  mov     rbx, [rdi+rsi+8]
0x1800ae237  test    rbx, rbx
0x1800ae23a  jz      loc_1800AE2F0
0x1800ae240  lea     r8, [rsp+270h+var_200]
0x1800ae245  mov     rcx, rbx
0x1800ae248  call    sqlite3BtreeBeginTrans
0x1800ae24d  xor     r10d, r10d
0x1800ae250  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae254  mov     r12d, eax
0x1800ae257  test    eax, eax
0x1800ae259  jnz     loc_1800B3D63
0x1800ae25f  test    byte ptr [r15+0C8h], 20h
0x1800ae267  jz      loc_1800AE2F9
0x1800ae26d  cmp     [r14+8], r10d
0x1800ae271  jz      loc_1800AE2F9
0x1800ae277  cmp     [r13+65h], r10b
0x1800ae27b  jz      short loc_1800AE287
0x1800ae27d  cmp     dword ptr [r13+0DCh], 1
0x1800ae285  jle     short loc_1800AE2F9
0x1800ae287  mov     r8d, [r15+40h]
0x1800ae28b  test    r8d, r8d
0x1800ae28e  jnz     short loc_1800AE2A9
0x1800ae290  inc     dword ptr [r13+2F4h]
0x1800ae297  mov     r8d, [r13+2F0h]
0x1800ae29e  add     r8d, [r13+2F4h]
0x1800ae2a5  mov     [r15+40h], r8d
0x1800ae2a9  dec     r8d
0x1800ae2ac  xor     edx, edx
0x1800ae2ae  mov     rcx, r13
0x1800ae2b1  call    sqlite3VtabSavepoint
0x1800ae2b6  xor     r10d, r10d
0x1800ae2b9  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae2bd  mov     r12d, eax
0x1800ae2c0  test    eax, eax
0x1800ae2c2  jnz     short loc_1800AE2DA
0x1800ae2c4  mov     edx, [r15+40h]
0x1800ae2c8  mov     rcx, rbx
0x1800ae2cb  call    sqlite3BtreeBeginStmt
0x1800ae2d0  mov     r12d, eax
0x1800ae2d3  mov     dword ptr [rsp+270h+var_228], eax
0x1800ae2d7  xor     r10d, r10d
0x1800ae2da  mov     rax, [r13+2F8h]
0x1800ae2e1  mov     [r15+58h], rax
0x1800ae2e5  mov     rax, [r13+300h]
0x1800ae2ec  mov     [r15+60h], rax
  ... truncated ...
```
