# sqlite3VdbeExec

- ea: `0x1801eee30`
- end: `0x1801f53fe`
- name: `sqlite3VdbeExec`
- size: `26062`
- prototype: ``
- caller_count: `2`
- callee_count: `173`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18019a29c`
- `0x1801ea920`

## callees

- `0x1800bb480`
- `0x1800bc07c`
- `0x1800bc094`
- `0x180196800`
- `0x180197d4c`
- `0x180197dd0`
- `0x18019a88c`
- `0x18019b114`
- `0x1801a6138`
- `0x1801a6450`
- `0x1801aa0d0`
- `0x1801b77bc`
- `0x1801b7ecc`
- `0x1801c50ec`
- `0x1801c66a8`
- `0x1801c844c`
- `0x1801c8498`
- `0x1801c84f0`
- `0x1801c851c`
- `0x1801c8590`
- `0x1801c85a8`
- `0x1801c89a8`
- `0x1801c8aa0`
- `0x1801c8af0`
- `0x1801c8b5c`
- `0x1801c8b6c`
- `0x1801c8b78`
- `0x1801c8b84`
- `0x1801c8f90`
- `0x1801c8fdc`
- `0x1801c901c`
- `0x1801c902c`
- `0x1801c90b4`
- `0x1801c9160`
- `0x1801c9238`
- `0x1801c96c8`
- `0x1801c9c08`
- `0x1801c9c28`
- `0x1801c9fe4`
- `0x1801ca004`
- `0x1801ca014`
- `0x1801ca050`
- `0x1801ca0f0`
- `0x1801ca140`
- `0x1801ca1c4`
- `0x1801ca7cc`
- `0x1801ca80c`
- `0x1801ca82c`
- `0x1801ca9d8`
- `0x1801caa34`

## string_xrefs

- `0x1801f4e38`: `cannot commit transaction - SQL statements in progress`
- `0x1801f4ee2`: `cannot rollback - no transaction is active`
- `0x1801f4ee9`: `cannot commit - no transaction is active`
- `0x1801f4f07`: `cannot open savepoint - SQL statements in progress`

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
  __int64 v27; // rdx
  __int64 v28; // r8
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  int v33; // r8d
  int v34; // edx
  unsigned int v35; // eax
  __int64 v36; // rdi
  __int64 v37; // rbx
  __int64 v38; // rdx
  __int64 v39; // rsi
  __int64 v40; // rdi
  __int64 v41; // rbx
  unsigned int v42; // eax
  int v43; // r8d
  unsigned int v44; // eax
  unsigned int v45; // ebx
  _BYTE *v46; // rsi
  unsigned int v47; // ebx
  __int64 v48; // rbx
  unsigned int v49; // eax
  _QWORD *v50; // rax
  _QWORD *v51; // rdi
  __int64 v52; // rax
  _QWORD *v53; // r15
  unsigned int m; // edi
  int v55; // eax
  unsigned int *v56; // r12
  int v57; // esi
  unsigned int v58; // eax
  int v59; // eax
  __int64 v60; // r8
  unsigned int v61; // eax
  int *v62; // r13
  int v63; // r12d
  __int64 v64; // rcx
  int v65; // ebx
  int v66; // esi
  unsigned int v67; // eax
  int v68; // ebx
  unsigned int v69; // r12d
  __int64 n; // rax
  _QWORD *v71; // rcx
  __int64 v72; // r13
  unsigned int v73; // eax
  __int64 v74; // r9
  unsigned int v75; // eax
  bool v76; // zf
  int v77; // ebx
  int v78; // ebx
  int v79; // ebx
  int v80; // ebx
  __int64 v81; // rcx
  __int64 *v82; // rbx
  int v83; // r9d
  __int64 v84; // rdx
  char v85; // di
  __int64 v86; // r8
  __int64 v87; // rcx
  __int64 v88; // rax
  __int16 v89; // ax
  __int64 v90; // rdx
  __int64 v91; // rdi
  int *v92; // r11
  __int64 v93; // r13
  int v94; // r9d
  __int64 **v95; // rbx
  __int64 v96; // rdx
  __int64 *v97; // r15
  __int64 v98; // rsi
  __int64 v99; // rax
  unsigned int v100; // eax
  __int64 *v101; // rdx
  int v102; // eax
  __int64 v103; // rcx
  int v104; // ebx
  int v105; // ebx
  int v106; // ebx
  int v107; // ebx
  int v108; // eax
  bool v109; // zf
  __int64 v110; // r8
  __int64 v111; // r9
  unsigned __int64 v112; // rcx
  unsigned int v113; // edx
  int v114; // eax
  int v115; // eax
  int v116; // eax
  __int64 v117; // rax
  __int64 v118; // rbx
  __int16 v119; // ax
  __int64 v120; // rdx
  __int64 v121; // rcx
  __int64 v122; // rcx
  int v123; // eax
  __int64 v124; // rcx
  __int64 v125; // rax
  int v126; // r13d
  __int64 v127; // rsi
  __int64 v128; // rdi
  __int16 v129; // r15
  __int64 v130; // rax
  __int16 v131; // cx
  __int64 v132; // r12
  _BYTE *v133; // rcx
  BOOL v134; // ecx
  __int64 v135; // rdx
  __int64 v136; // rax
  __int64 v137; // rbx
  int v138; // eax
  unsigned __int64 v139; // rdx
  __int64 v140; // rcx
  __int64 v141; // rcx
  __int64 v142; // rcx
  __int64 v143; // rcx
  __int16 v144; // ax
  int v145; // ecx
  bool v146; // zf
  __int64 v147; // rcx
  __int64 v148; // rax
  __int64 v149; // rbx
  __int64 v150; // rcx
  int *v151; // rsi
  __int64 v152; // rdx
  unsigned int v153; // eax
  int v154; // eax
  _QWORD *v155; // rdi
  unsigned int v156; // eax
  char v157; // r15
  __int64 v158; // rax
  unsigned int v159; // eax
  unsigned int v160; // eax
  __int64 v161; // rcx
  __int64 v162; // rax
  __int64 v163; // rbx
  unsigned int v164; // eax
  __int64 v165; // rcx
  __int64 v166; // rax
  __int64 v167; // rcx
  __int128 v168; // xmm1
  __int128 v169; // xmm0
  __int64 v170; // rdi
  __int64 v171; // rbx
  __int64 v172; // rcx
  unsigned int v173; // eax
  bool v174; // zf
  __int64 v175; // rax
  __int64 v176; // rdi
  int v177; // ecx
  unsigned int v178; // edx
  int v179; // ebx
  int v180; // ebx
  int v181; // ebx
  int v182; // ebx
  __int64 v183; // rbx
  unsigned int v184; // eax
  __int64 v185; // rcx
  __int64 v186; // rax
  __int64 v187; // rbx
  unsigned int v188; // eax
  int v189; // ebx
  int v190; // eax
  int v191; // ebx
  __int64 *v192; // rax
  __int64 v193; // r8
  __int64 v194; // rdx
  __int16 v195; // cx
  __int16 v196; // cx
  __int64 v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rdx
  __int64 v200; // rcx
  __int64 v201; // rbx
  unsigned int v202; // edi
  unsigned int v203; // eax
  int v204; // ebx
  int v205; // ecx
  int v206; // ebx
  int v207; // ebx
  int v208; // ebx
  int v209; // ebx
  int v210; // ebx
  bool v211; // zf
  bool v212; // zf
  __int64 v213; // r8
  __int64 jj; // rax
  int *v215; // r12
  int *v216; // r13
  __int64 v217; // rsi
  int v218; // edi
  int v219; // r15d
  __int64 v220; // rbx
  __int64 v221; // rcx
  __int64 *v222; // rsi
  __int64 v223; // rdx
  __int64 v224; // r15
  __int64 v225; // rcx
  void *v226; // rcx
  __int64 v227; // r8
  int v228; // eax
  int v229; // edi
  __int64 v230; // rbx
  __int64 v231; // rsi
  int v232; // eax
  __int64 v233; // rsi
  bool v234; // sf
  int v235; // eax
  __int64 v236; // rax
  __int64 v237; // rbx
  __int64 v238; // r13
  __int64 v239; // r15
  __int16 v240; // si
  __int16 v241; // di
  bool v242; // zf
  __int64 v243; // rax
  char v244; // cl
  __int64 v245; // rcx
  char v246; // cl
  unsigned __int8 v247; // al
  int v248; // eax
  int v249; // ebx
  int v250; // ebx
  int v251; // ebx
  int v252; // ebx
  unsigned int v253; // eax
  __int64 v254; // rcx
  __int64 v255; // rax
  __int64 v256; // rax
  __int64 v257; // rcx
  __int64 v258; // rax
  __int64 v259; // rdx
  __int64 v260; // rcx
  __int64 v261; // rdi
  __int64 **v262; // rcx
  __int64 *v263; // rbx
  __int64 v264; // rsi
  int v265; // eax
  int v266; // ebx
  int v267; // ebx
  int v268; // ebx
  __int64 v269; // rax
  __int64 v270; // rbx
  __int64 v271; // rdi
  int v272; // edx
  int v273; // eax
  const char *v274; // rax
  __int64 v275; // rbx
  unsigned __int64 v276; // rax
  unsigned __int64 v277; // rdx
  int v278; // r8d
  unsigned __int8 v279; // cf
  __int64 v280; // rdx
  __int64 v281; // rcx
  int v282; // ebx
  int v283; // ebx
  int v284; // ebx
  int v285; // ebx
  __int64 v286; // rax
  unsigned int **v287; // rax
  unsigned int *v288; // rcx
  __int64 v289; // rcx
  __int64 v290; // rax
  __int64 v291; // rax
  int v292; // eax
  int v293; // ebx
  int v294; // ebx
  int v295; // ebx
  int v296; // ebx
  int v297; // esi
  __int64 v298; // rdi
  __int64 v299; // rbx
  int v300; // eax
  __int64 v301; // rdi
  int v302; // eax
  __int64 v303; // rbx
  __int64 v304; // rax
  __int64 v305; // rdx
  __int64 v306; // rbx
  int v307; // eax
  __int64 v308; // rcx
  __int64 v309; // rbx
  int v310; // edi
  __int16 v311; // si
  __int16 v312; // si
  int v313; // esi
  __int64 v314; // rdi
  __int64 kk; // rbx
  int v316; // eax
  __int16 v317; // ax
  int v318; // ebx
  int v319; // ebx
  int v320; // ebx
  int v321; // ebx
  __int64 v322; // rax
  __int64 v323; // rax
  __int64 v324; // r8
  __int64 v325; // rdx
  __int64 v326; // rcx
  _QWORD *v327; // rbx
  int v328; // ebx
  int v329; // ebx
  int v330; // ebx
  __int64 v331; // rsi
  int v332; // eax
  unsigned int v333; // edi
  unsigned int *v334; // r8
  unsigned int v335; // r9d
  int v336; // ecx
  int v337; // edx
  __int64 v338; // r12
  int v339; // r13d
  __int64 v340; // r15
  unsigned int v341; // eax
  __int64 v342; // rbx
  unsigned int v343; // eax
  __int64 v344; // rax
  int v345; // ebx
  int v346; // ebx
  int v347; // ebx
  int v348; // ebx
  __int64 v349; // rcx
  __int64 v350; // rax
  __int64 v351; // rcx
  unsigned int v352; // eax
  unsigned int **v353; // rax
  unsigned int *v354; // rdx
  char *v355; // rdi
  __int64 v356; // r15
  int v357; // r13d
  int v358; // r12d
  int v359; // eax
  int *v360; // rcx
  int *v361; // rsi
  char v362; // al
  int *v363; // rbx
  __int16 v364; // ax
  int *v365; // rax
  int *j; // rbx
  __int16 v367; // cx
  unsigned __int64 v368; // rdx
  int v369; // edx
  __int64 v370; // rax
  __int64 v371; // rcx
  __int64 v372; // rax
  double v373; // xmm0_8
  unsigned int v374; // edi
  unsigned int v375; // esi
  __int64 v376; // rax
  int v377; // eax
  int v378; // ecx
  unsigned __int64 v379; // rax
  __int64 v380; // rdi
  int v381; // edx
  unsigned __int64 v382; // rax
  int v383; // ecx
  unsigned __int64 v384; // rax
  __int64 v385; // rbx
  unsigned int *v386; // r15
  int v387; // eax
  _BYTE *v388; // rdi
  _BYTE *v389; // rbx
  _BYTE *v390; // rsi
  int *v391; // rdi
  __int64 v392; // r15
  __int64 v393; // rax
  unsigned __int64 v394; // rcx
  __int64 v395; // rdx
  int v396; // eax
  int v397; // eax
  int v398; // eax
  int v399; // eax
  unsigned __int64 v400; // rcx
  unsigned __int64 v401; // rcx
  int v402; // eax
  char *v403; // rdi
  char v404; // al
  __int64 i; // rbx
  __int16 v406; // cx
  __int16 v407; // cx
  __int64 v408; // r12
  __int64 v409; // r15
  __int64 v410; // rdi
  int v411; // esi
  _WORD *v412; // r9
  bool v413; // zf
  __int16 v414; // ax
  bool v415; // zf
  const char *v416; // rax
  __int64 v417; // rax
  unsigned int v418; // r12d
  __int64 v419; // rbx
  unsigned int *v420; // r13
  int v421; // eax
  __int64 v422; // rdi
  __int64 v423; // rdx
  int v424; // eax
  unsigned int v425; // eax
  unsigned int v426; // eax
  unsigned int *v427; // r15
  unsigned __int8 *Payload; // rcx
  __int64 v429; // rcx
  int v430; // eax
  int *v431; // rdi
  unsigned int v432; // eax
  int v433; // eax
  unsigned __int16 *v434; // rsi
  __int64 v435; // rcx
  __int64 v436; // rax
  __int64 v437; // rcx
  unsigned int v438; // eax
  __int64 v439; // r12
  unsigned int v440; // r14d
  unsigned __int8 *v441; // rdi
  unsigned __int64 v442; // rsi
  unsigned __int64 v443; // r13
  unsigned int *v444; // rcx
  __int64 v445; // rax
  int v446; // edi
  __int64 v447; // rdx
  int v448; // eax
  __int64 v449; // rax
  __int64 v450; // rdi
  const void *v451; // rsi
  size_t v452; // rbx
  __int64 v453; // rdx
  char v454; // al
  unsigned int v455; // eax
  unsigned int v456; // eax
  __int64 v457; // rcx
  __int64 v458; // rdx
  __int64 v459; // rax
  int v460; // ebx
  int v461; // ebx
  int v462; // ebx
  __int64 v463; // rdi
  __int64 v464; // rdx
  __int64 v465; // rsi
  __int64 v466; // rdi
  __int64 v467; // rbx
  __int64 v468; // rdi
  __int64 v469; // rbx
  unsigned int updated; // eax
  __int64 k; // rax
  __int64 v472; // rbx
  __int64 v473; // rdx
  __int64 v474; // rax
  char v475; // cl
  __int64 v476; // rdx
  int v477; // ebx
  int v478; // ebx
  int v479; // ebx
  __int64 v480; // rax
  __int64 v481; // rdi
  __int64 v482; // rsi
  __int64 v483; // r15
  __int16 v484; // dx
  unsigned __int8 v485; // bl
  int v486; // ecx
  __int64 v487; // rdx
  __int64 v488; // r8
  int v489; // ecx
  int v490; // ecx
  int v491; // ecx
  __int128 v492; // rax
  __int64 v493; // rax
  int v494; // eax
  __int16 v495; // ax
  double v496; // xmm6_8
  __int64 v497; // rdx
  double v498; // xmm0_8
  __int64 v499; // rbx
  __int64 v500; // rdx
  __int64 v501; // rax
  double v502; // xmm0_8
  __int16 v503; // ax
  __int64 v504; // r13
  __int16 v505; // r12
  __int64 v506; // rdi
  __int64 v507; // rbx
  int v508; // eax
  __int16 v509; // si
  int v510; // eax
  unsigned __int64 v511; // r15
  int v512; // ebx
  int v513; // ebx
  int v514; // ebx
  __int64 v515; // rbx
  __int64 Cursor; // rax
  int v517; // ecx
  __int64 v518; // rdi
  __int64 v519; // rbx
  int v520; // r12d
  __int64 v521; // rcx
  __int64 v522; // r15
  __int64 v523; // rax
  __int64 v524; // r13
  int v525; // esi
  unsigned __int8 v526; // cl
  unsigned __int8 v527; // al
  __int64 v528; // rbx
  __int64 v529; // r8
  __int64 v530; // rax
  __int64 v531; // rcx
  unsigned int v532; // eax
  int v533; // ebx
  int v534; // ebx
  int v535; // ebx
  int v536; // ebx
  __int64 v537; // rax
  __int64 v538; // rdx
  __int64 v539; // rcx
  __int64 v540; // rax
  __int64 v541; // rdx
  __int64 v542; // rsi
  __int64 v543; // rdx
  __int64 v544; // rcx
  unsigned int v545; // eax
  __int64 v546; // rax
  _QWORD *v547; // r15
  unsigned int v548; // eax
  unsigned int v549; // eax
  __int64 v550; // r13
  _DWORD *v551; // r12
  __int64 v552; // rdi
  unsigned int v553; // ebx
  __int64 v554; // rax
  __int64 v555; // rcx
  __int64 v556; // rax
  __int64 v557; // r9
  __int64 v558; // rdx
  __int64 v559; // rbx
  int v560; // ecx
  __int64 v561; // rcx
  __int64 v562; // rdx
  __int64 v563; // rax
  int v564; // ebx
  int v565; // ebx
  int v566; // ebx
  int v567; // ebx
  __int64 v568; // rcx
  __int64 v569; // rdx
  __int64 v570; // rax
  __int64 v571; // rbx
  __int64 v572; // r8
  __int64 v573; // rdi
  __int64 v574; // rsi
  __int16 v575; // r8
  __int64 v576; // r9
  unsigned int v577; // eax
  __int64 v578; // rcx
  void (__fastcall *v579)(_QWORD, __int64, __int64, _QWORD, __int64); // rax
  __int64 v580; // rdx
  __int64 *v581; // rsi
  __int64 v582; // rdi
  unsigned int v583; // eax
  __int64 v584; // rax
  __int64 v585; // rcx
  __int64 *v586; // rbx
  __int64 v587; // rax
  int v588; // ebx
  unsigned int v589; // eax
  _QWORD *v590; // rax
  __int64 v591; // rdx
  __int64 v592; // rdx
  int v593; // eax
  __int64 v594; // rcx
  __int64 v595; // rax
  __int64 v596; // rbx
  int v597; // edi
  __int64 v598; // rax
  unsigned int v599; // eax
  bool v600; // sf
  __int64 v601; // rcx
  unsigned int v602; // eax
  __int64 v603; // r8
  int v604; // ebx
  int v605; // ebx
  int v606; // ebx
  int v607; // ebx
  __int64 v608; // rbx
  __int64 v609; // rdi
  unsigned int v610; // eax
  unsigned int v611; // eax
  int Writeable; // eax
  unsigned int v613; // eax
  __int64 v614; // rcx
  __int64 v615; // r8
  __int64 v616; // rdx
  __int64 v617; // rax
  unsigned int v618; // eax
  int v619; // r15d
  __int64 v620; // rbx
  unsigned int v621; // eax
  __int64 v622; // rax
  __int64 v623; // rdx
  __int64 v624; // rcx
  __int64 v625; // rdi
  __int64 v626; // rbx
  __int64 v627; // rax
  __int64 *v628; // rcx
  __int64 v629; // rbx
  unsigned int v630; // eax
  __int64 v631; // rdi
  __int64 v632; // rbx
  unsigned int v633; // eax
  unsigned int v634; // eax
  __int64 v635; // rax
  __int64 v636; // rcx
  __int64 v637; // rdi
  __int64 v638; // rbx
  unsigned int v639; // eax
  __int16 v640; // r8
  __int64 v641; // rcx
  __int64 v642; // r9
  __int64 v643; // rcx
  __int64 v644; // rax
  __int64 v645; // rdi
  __int64 v646; // rsi
  __int64 v647; // rcx
  int IsValidNN; // eax
  unsigned int v649; // eax
  __int64 v650; // rdx
  __int64 v651; // rbx
  __int64 valid; // rax
  __int64 v653; // rcx
  __int64 v654; // rax
  _QWORD *v655; // rbx
  __int64 v656; // rdi
  __int64 v657; // rax
  unsigned int v658; // eax
  __int64 v659; // rdx
  unsigned int v660; // eax
  int v661; // eax
  int v662; // ebx
  int v663; // ebx
  int v664; // ebx
  int v665; // ebx
  __int64 v666; // rcx
  __int64 v667; // rdx
  __int64 v668; // rax
  unsigned int v669; // eax
  __int64 v670; // rdx
  __int64 v671; // rbx
  unsigned int v672; // edi
  __int64 v673; // rcx
  __int64 v674; // rdx
  __int64 v675; // rcx
  __int64 v676; // rcx
  __int64 v677; // rax
  __int64 v678; // rbx
  unsigned int v679; // eax
  unsigned int v680; // eax
  __int64 v681; // rdx
  __int64 v682; // rcx
  __int64 v683; // r8
  int v684; // ebx
  int v685; // ebx
  int v686; // ebx
  int v687; // ebx
  __int64 v688; // rbx
  __int64 v689; // rcx
  unsigned int inited; // eax
  __int64 v691; // rbx
  int v692; // eax
  __int64 v693; // r8
  __int64 v694; // rbx
  __int64 v695; // rbx
  char v696; // di
  int v697; // esi
  unsigned int v698; // eax
  const char *v699; // r8
  __int64 v700; // rax
  __int64 v701; // rcx
  _QWORD *v702; // rbx
  __int64 v703; // r8
  __int64 v704; // r9
  unsigned int v705; // eax
  int v706; // ebx
  int v707; // ebx
  int v708; // ebx
  int v709; // ebx
  __int64 v710; // rax
  __int64 v711; // rdi
  __int64 v712; // rbx
  __int64 v713; // rdx
  __int64 v714; // r8
  __int64 v715; // rdi
  int v716; // eax
  __int64 v717; // rdx
  int v718; // r9d
  __int64 v719; // rbx
  __int64 v720; // r9
  unsigned __int64 v721; // rsi
  __int64 (__fastcall *v722)(_QWORD); // rax
  __int64 v723; // rbx
  int v724; // eax
  __int64 v725; // rcx
  int v726; // ebx
  int v727; // ebx
  __int64 v728; // rdi
  __int64 v729; // rbx
  __int64 v730; // rcx
  _DWORD *v731; // rbx
  __int64 v732; // r8
  int v733; // edx
  __int64 v734; // rsi
  __int64 v735; // rbx
  __int64 v736; // rdx
  __int64 v737; // rdx
  int v738; // eax
  __int64 v739; // rcx
  _QWORD *v740; // rdi
  _QWORD *v741; // rbx
  _DWORD *v742; // r8
  __int64 v743; // rax
  __int64 v744; // rdx
  int v745; // eax
  const char *v746; // rax
  int v747; // ebx
  int v748; // ebx
  int v749; // ebx
  int v750; // ebx
  __int64 v751; // rbx
  unsigned int v752; // eax
  int v753; // ebx
  int v754; // ebx
  int v755; // ebx
  __int64 v756; // rax
  __int64 *v757; // rbx
  __int64 v758; // rdi
  __int64 v759; // r9
  __int64 v760; // rax
  __int64 v761; // rax
  __int64 v762; // rax
  __int64 v763; // rbx
  unsigned int v764; // eax
  __int64 v765; // rax
  __int64 v766; // r15
  _QWORD *v767; // rsi
  __int64 v768; // rcx
  __int64 *v769; // rdi
  __int64 v770; // rbx
  __int64 v771; // r9
  int v772; // ebx
  int v773; // ebx
  int v774; // ebx
  int v775; // ebx
  _QWORD *v776; // rdi
  __int64 v777; // rdx
  __int64 v778; // rbx
  unsigned int Page; // eax
  _QWORD *v780; // rbx
  int v781; // esi
  __int64 v782; // rbx
  __int64 v783; // rdi
  unsigned int v784; // eax
  __int64 v785; // rdi
  __int64 v786; // rax
  __int64 v787; // rbx
  __int64 *v788; // rsi
  __int64 v789; // r15
  __int16 v790; // ax
  unsigned int v791; // eax
  const char *v792; // rax
  __int64 v793; // rdi
  _QWORD *v794; // rax
  _QWORD *v795; // rbx
  __int64 v796; // rax
  int v797; // ebx
  int v798; // ebx
  int v799; // ebx
  char v800; // al
  const char *v801; // r9
  __int64 v802; // rbx
  __int64 v803; // rbx
  int v804; // eax
  int ii; // ecx
  __int64 v806; // rax
  __int64 v807; // rbx
  unsigned __int64 v808; // rax
  unsigned __int64 v809; // r8
  __int64 v810; // rdx
  __int64 v811; // rcx
  __int64 v812; // rdx
  const char *v813; // r8
  const char *v814; // rdx
  __int64 v815; // rdx
  int v816; // ebx
  int v817; // ecx
  char v818; // al
  const char *v819; // rdx
  unsigned int v820; // eax
  int v821; // ecx
  unsigned int v822; // eax
  __int64 v823; // rbx
  const char *v824; // rax
  unsigned __int64 v825; // rdx
  __int64 (__fastcall *v826)(__int64); // rax
  __int64 v827; // rcx
  int v828; // eax
  __int64 v830; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v831; // [rsp+48h] [rbp-C0h]
  unsigned int v832; // [rsp+4Ch] [rbp-BCh]
  unsigned int Table; // [rsp+50h] [rbp-B8h]
  __int64 v834; // [rsp+58h] [rbp-B0h]
  __int64 v835; // [rsp+60h] [rbp-A8h]
  unsigned int *v837; // [rsp+70h] [rbp-98h] BYREF
  __int64 v838; // [rsp+78h] [rbp-90h] BYREF
  __int64 v839; // [rsp+80h] [rbp-88h]
  int *v840; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v841; // [rsp+90h] [rbp-78h] BYREF
  char v842; // [rsp+94h] [rbp-74h]
  unsigned int v843; // [rsp+98h] [rbp-70h]
  __int128 v844; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v845; // [rsp+B0h] [rbp-58h]
  __int128 v846; // [rsp+C0h] [rbp-48h]
  int v847; // [rsp+D0h] [rbp-38h]
  __int64 v848; // [rsp+D8h] [rbp-30h] BYREF
  int v849; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v850; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v851; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v852; // [rsp+F8h] [rbp-10h]
  __int128 v853; // [rsp+100h] [rbp-8h] BYREF
  __int128 v854; // [rsp+110h] [rbp+8h]
  __int128 v855; // [rsp+120h] [rbp+18h]
  __int64 v856; // [rsp+130h] [rbp+28h]
  __int128 v857; // [rsp+138h] [rbp+30h] BYREF
  __int128 v858; // [rsp+148h] [rbp+40h]
  __int128 v859; // [rsp+158h] [rbp+50h]
  __int64 v860; // [rsp+168h] [rbp+60h]
  _OWORD v861[2]; // [rsp+170h] [rbp+68h] BYREF
  __int128 v862; // [rsp+190h] [rbp+88h]
  __int64 v863; // [rsp+1A0h] [rbp+98h]
  char v864; // [rsp+1A8h] [rbp+A0h] BYREF
  __int16 v865; // [rsp+1A9h] [rbp+A1h]
  char v866; // [rsp+1ABh] [rbp+A3h]
  int v867; // [rsp+1ACh] [rbp+A4h]
  int v868; // [rsp+1F8h] [rbp+F0h]
  __int64 v869; // [rsp+1FCh] [rbp+F4h] BYREF

  v2 = *a1;
  v3 = 0;
  v4 = a1;
  v5 = a1[17];
  v6 = (unsigned __int8 *)v5;
  v7 = a1[13];
  v8 = 0;
  v9 = *(_BYTE *)(*a1 + 100);
  v831 = v9;
  v834 = v5;
  v839 = *a1;
  v842 = 0;
  v852 = 0;
  v835 = v7;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter(a1, a2, v5, 0);
    v8 = v852;
    v5 = (__int64)v6;
    v3 = 0;
  }
  if ( *(_QWORD *)(v2 + 528) )
    v851 = (unsigned int)(*(_DWORD *)(v2 + 544) - *((_DWORD *)v4 + 57) % *(_DWORD *)(v2 + 544));
  else
    v851 = -1;
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
  v832 = 0;
  v847 = 0;
  v6 = (unsigned __int8 *)(v5 + 24 * v12);
LABEL_9:
  v15 = *v6;
  v16 = v10 + v8;
  v848 = (__int64)v6;
  v852 = v16;
  if ( (unsigned int)v15 > 0x5C )
  {
    if ( (unsigned int)v15 <= 0x8C )
    {
      if ( (_DWORD)v15 == 140 )
      {
        v653 = *((int *)v6 + 1);
        LODWORD(v838) = 0;
        *(_QWORD *)&v846 = 0;
        v654 = v4[15];
        v844 = 0;
        v845 = 0;
        v655 = *(_QWORD **)(v654 + 8 * v653);
        v656 = v655[6];
        *(_QWORD *)&v844 = v655[7];
        WORD6(v845) = *((_WORD *)v6 + 6);
        v657 = *((int *)v6 + 2);
        BYTE14(v845) = 0;
        *((_QWORD *)&v844 + 1) = v7 + 56 * v657;
        v658 = sqlite3BtreeIndexMoveto(v656, &v844, &v838);
        v3 = 0;
        Table = v658;
        v14 = v658;
        if ( v658 )
          goto LABEL_1546;
        if ( (_DWORD)v838 )
        {
          if ( *((_WORD *)v6 + 1) )
          {
            v661 = sqlite3WritableSchema(v2);
            v3 = 0;
            if ( !v661 )
            {
              v820 = sqlite3ReportError(779, 99656, "index corruption");
              goto LABEL_1530;
            }
          }
        }
        else
        {
          LOBYTE(v659) = 4;
          v660 = sqlite3BtreeDelete(v656, v659);
          v3 = 0;
          Table = v660;
          v14 = v660;
          if ( v660 )
            goto LABEL_1546;
        }
        v655[4] = 0;
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
                v457 = *(_QWORD *)(v2 + 32);
                v458 = *((unsigned int *)v6 + 3);
                v459 = 32LL * *((int *)v6 + 1);
                LODWORD(v838) = 0;
                sqlite3BtreeGetMeta(*(_QWORD *)(v459 + v457 + 8), v458, &v838);
                v287 = (unsigned int **)out2Prerelease(v4, v6);
                v288 = (unsigned int *)(int)v838;
                goto LABEL_536;
              }
              v345 = v15 - 94;
              if ( v345 )
              {
                v346 = v345 - 1;
                if ( v346 )
                {
                  v347 = v346 - 1;
                  if ( !v347 )
                  {
                    v403 = (char *)*((_QWORD *)v6 + 2);
                    v404 = *v403;
                    for ( i = v7 + 56LL * *((int *)v6 + 1); ; i += 56 )
                    {
                      LOBYTE(v5) = v831;
                      LOBYTE(v13) = v404;
                      applyAffinity(i, v13, v5);
                      if ( *v403 == 69 )
                      {
                        v406 = *(_WORD *)(i + 20);
                        if ( (v406 & 4) != 0 )
                        {
                          v13 = *(_QWORD *)i;
                          v5 = 0xFFFFFFFFFFFFLL;
                          if ( (unsigned __int64)(*(_QWORD *)i + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                          {
                            v407 = v406 & 0xFFF1 | 8;
                            *(double *)i = (double)(int)v13;
                          }
                          else
                          {
                            v407 = v406 & 0xFFDB | 0x20;
                          }
                          *(_WORD *)(i + 20) = v407;
                        }
                      }
                      v10 = 1;
                      v3 = 0;
                      v404 = *++v403;
                      if ( !*v403 )
                        break;
                    }
                    goto LABEL_1404;
                  }
                  v348 = v347 - 1;
                  if ( v348 )
                  {
                    if ( v348 != 1 )
                      goto LABEL_53;
                    v349 = *((int *)v6 + 1);
                    v350 = v4[15];
                    v837 = 0;
                    v351 = *(_QWORD *)(v350 + 8 * v349);
                    if ( *((_DWORD *)v6 + 3) )
                    {
                      v837 = (unsigned int *)sqlite3BtreeRowCountEst(*(_QWORD *)(v351 + 48));
                    }
                    else
                    {
                      v352 = sqlite3BtreeCount(v2, *(_QWORD *)(v351 + 48), &v837);
                      v3 = 0;
                      Table = v352;
                      v14 = v352;
                      if ( v352 )
                        goto LABEL_1546;
                    }
                    v353 = (unsigned int **)out2Prerelease(v4, v6);
                    *v353 = v837;
                    goto LABEL_1308;
                  }
                  v354 = 0;
                  v355 = (char *)*((_QWORD *)v6 + 2);
                  v356 = 0;
                  v357 = *((_DWORD *)v6 + 3);
                  v358 = 0;
                  v359 = *((_DWORD *)v6 + 2);
                  v360 = (int *)(v7 + 56LL * *((int *)v6 + 1));
                  LODWORD(v838) = 0;
                  v837 = 0;
                  v840 = v360;
                  v361 = &v360[14 * (v359 - (int)v10)];
                  v848 = (__int64)v361;
                  if ( v355 )
                  {
                    v362 = *v355;
                    v363 = v360;
                    do
                    {
                      LOBYTE(v5) = v831;
                      LOBYTE(v354) = v362;
                      applyAffinity(v363, v354, v5);
                      if ( *v355 == 69 )
                      {
                        v364 = *((_WORD *)v363 + 10);
                        if ( (v364 & 4) != 0 )
                          *((_WORD *)v363 + 10) = v364 & 0xFFDB | 0x20;
                      }
                      v10 = 1;
                      v363 += 14;
                      ++v355;
                      v3 = 0;
                      v362 = *v355;
                    }
                    while ( *v355 );
                    v358 = v838;
                    v354 = v837;
                    v361 = (int *)v848;
                  }
                  v365 = v840;
                  for ( j = v361; ; j -= 14 )
                  {
                    v367 = *((_WORD *)j + 10);
                    if ( ((unsigned __int8)v367 & (unsigned __int8)v10) != 0 )
                    {
                      j[9] = (v367 & 0x400) != 0 ? 0xA : 0;
                      v358 += v10;
                    }
                    else
                    {
                      if ( (v367 & 0x24) != 0 )
                      {
                        v368 = *(_QWORD *)j;
                        if ( *(__int64 *)j < 0 )
                          v368 = ~v368;
                        v358 += v10;
                        if ( v368 <= 0x7F )
                        {
                          if ( (v10 & *(_QWORD *)j) == *(_QWORD *)j && *((_BYTE *)a1 + 197) >= 4u )
                          {
                            v369 = v368 + 8;
                          }
                          else
                          {
                            v356 += v10;
                            v369 = v10;
                          }
                          v370 = 36;
                          v371 = (__int64)j;
                          goto LABEL_684;
                        }
                        if ( v368 <= 0x7FFF )
                        {
                          v372 = 2;
                          goto LABEL_673;
                        }
                        if ( v368 > 0x7FFFFF )
                        {
                          if ( v368 > 0x7FFFFFFF )
                          {
                            if ( v368 > 0x7FFFFFFFFFFFLL )
                            {
                              v356 += 8;
                              if ( (v367 & 0x20) != 0 )
                              {
                                v373 = (double)(int)*(_QWORD *)j;
                                v369 = 7;
                                *((_WORD *)j + 10) = v367 & 0xFFD7 | 8;
                                *(double *)j = v373;
                              }
                              else
                              {
                                v369 = 6;
                              }
                            }
                            else
                            {
                              v356 += 6;
                              v369 = 5;
                            }
                          }
                          else
                          {
                            v372 = 4;
LABEL_673:
                            v356 += v372;
                            v369 = v372;
                          }
                        }
                        else
                        {
                          v356 += 3;
                          v369 = 3;
                        }
                        v371 = 36;
                        v370 = (__int64)j;
LABEL_684:
                        *(_DWORD *)(v371 + v370) = v369;
                        goto LABEL_696;
                      }
                      if ( (v367 & 8) != 0 )
                      {
                        v358 += v10;
                        j[9] = 7;
                        v356 += 8;
                        goto LABEL_697;
                      }
                      v374 = j[4];
                      v375 = ((v367 & 2 | 0x18u) >> 1) + 2 * v374;
                      if ( (v367 & 0x400) != 0 )
                      {
                        v376 = *j;
                        v375 += 2 * v376;
                        if ( v356 )
                        {
                          v377 = sqlite3VdbeMemExpandBlob(j);
                          v3 = 0;
                          if ( v377 )
                            goto LABEL_1541;
                          v374 += *j;
                          v10 = 1;
                        }
                        else
                        {
                          v837 = (unsigned int *)((char *)v354 + v376);
                        }
                      }
                      v378 = v10;
                      v356 += v374;
                      v379 = v375;
                      while ( 1 )
                      {
                        v379 >>= 7;
                        if ( !v379 )
                          break;
                        v378 += v10;
                      }
                      v358 += v378;
                      j[9] = v375;
                    }
LABEL_696:
                    v365 = v840;
LABEL_697:
                    if ( j == v365 )
                    {
                      v380 = v835 + 56LL * v357;
                      if ( v358 <= 126 )
                        goto LABEL_707;
                      v381 = v10;
                      v382 = v358;
                      while ( 1 )
                      {
                        v382 >>= 7;
                        if ( !v382 )
                          break;
                        v381 += v10;
                      }
                      v358 += v381;
                      v383 = v10;
                      v384 = v358;
                      while ( 1 )
                      {
                        v384 >>= 7;
                        if ( !v384 )
                          break;
                        v383 += v10;
                      }
                      if ( v381 < v383 )
LABEL_707:
                        v358 += v10;
                      v385 = v356 + v358;
                      v386 = v837;
                      if ( (__int64)v837 + v385 <= *(int *)(v380 + 32) )
                      {
                        *(_QWORD *)(v380 + 8) = *(_QWORD *)(v380 + 40);
                        goto LABEL_712;
                      }
                      v2 = v839;
                      if ( (__int64)v837 + v385 <= *(int *)(v839 + 136) )
                      {
                        v387 = sqlite3VdbeMemClearAndResize(v380, (unsigned int)v385);
                        v3 = 0;
                        if ( v387 )
                          goto LABEL_858;
LABEL_712:
                        *(_DWORD *)(v380 + 16) = v385;
                        *(_WORD *)(v380 + 20) = 16;
                        if ( v386 )
                        {
                          *(_DWORD *)v380 = (_DWORD)v386;
                          *(_WORD *)(v380 + 20) = 1040;
                        }
                        v388 = *(_BYTE **)(v380 + 8);
                        v389 = &v388[v358];
                        if ( v358 >= 128 )
                        {
                          v390 = &v388[(int)sqlite3PutVarint(v388, v358)];
                          v3 = 0;
                        }
                        else
                        {
                          *v388 = v358;
                          v390 = v388 + 1;
                        }
                        v391 = v840;
                        v392 = v848;
                        while ( 2 )
                        {
                          v393 = (unsigned int)v391[9];
                          if ( (unsigned int)v393 <= 7 )
                          {
                            v10 = 1;
                            *v390++ = v393;
                            if ( (_DWORD)v393 )
                            {
                              v394 = *(_QWORD *)v391;
                              v395 = *((unsigned __int8 *)qword_1802DD790 + v393);
                              v396 = *((unsigned __int8 *)qword_1802DD790 + v393) - 1;
                              if ( v396 )
                              {
                                v397 = v396 - 1;
                                if ( v397 )
                                {
                                  v398 = v397 - 1;
                                  if ( v398 )
                                  {
                                    v399 = v398 - 1;
                                    if ( v399 )
                                    {
                                      if ( v399 != 2 )
                                      {
                                        v389[7] = v394;
                                        v400 = v394 >> 8;
                                        v389[6] = v400;
                                        v394 = v400 >> 8;
                                      }
                                      v389[5] = v394;
                                      v401 = v394 >> 8;
                                      v389[4] = v401;
                                      v394 = v401 >> 8;
                                    }
                                    v389[3] = v394;
                                    v394 >>= 8;
                                  }
                                  v389[2] = v394;
                                  v394 >>= 8;
                                }
                                v389[1] = v394;
                                v394 >>= 8;
                              }
                              *v389 = v394;
                              v389 += v395;
                            }
                            goto LABEL_738;
                          }
                          if ( (unsigned int)v393 >= 0x80 )
                          {
                            v402 = sqlite3PutVarint(v390, (unsigned int)v391[9]);
                            v3 = 0;
                            v390 += v402;
                            if ( v391[4] )
                              goto LABEL_736;
LABEL_737:
                            v10 = 1;
                          }
                          else
                          {
                            v10 = 1;
                            *v390++ = v393;
                            if ( (unsigned int)v393 >= 0xE && v391[4] > 0 )
                            {
LABEL_736:
                              memcpy_0(v389, *((const void **)v391 + 1), v391[4]);
                              v389 += v391[4];
                              v3 = 0;
                              goto LABEL_737;
                            }
                          }
LABEL_738:
                          if ( v391 == (int *)v392 )
                          {
                            v14 = Table;
                            v4 = a1;
                            goto LABEL_1403;
                          }
                          v391 += 14;
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
                    v354 = v837;
                  }
                }
                v408 = *((_QWORD *)v6 + 2);
                v409 = *(_QWORD *)(v408 + 8);
                v410 = v7 + 56LL * *((int *)v6 + 1);
                v411 = 0;
                if ( *(__int16 *)(v408 + 54) > 0 )
                {
                  while ( (*(_BYTE *)(v409 + 24LL * v411 + 18) & 0x60) != 0 )
                  {
                    if ( (*(_BYTE *)(v409 + 24LL * v411 + 18) & 0x20) == 0 )
                    {
                      if ( !*((_DWORD *)v6 + 3) )
                        break;
                      v410 += 56;
                    }
LABEL_773:
                    v411 += v10;
                    if ( v411 >= *(__int16 *)(v408 + 54) )
                    {
                      v14 = Table;
                      v5 = v834;
                      goto LABEL_976;
                    }
                  }
                  LOBYTE(v5) = v831;
                  LOBYTE(v13) = *(_BYTE *)(v409 + 24LL * v411 + 12);
                  applyAffinity(v410, v13, v5);
                  v412 = (_WORD *)(v410 + 20);
                  v10 = 1;
                  v13 = *(unsigned __int16 *)(v410 + 20);
                  if ( (v13 & 1) != 0 )
                    goto LABEL_772;
                  v5 = (*(_DWORD *)(v409 + 24LL * v411 + 8) >> 4) & 0xF;
                  switch ( (*(_DWORD *)(v409 + 24LL * v411 + 8) >> 4) & 0xF )
                  {
                    case 2:
                      v413 = (v13 & 0x10) == 0;
LABEL_771:
                      if ( v413 )
                      {
LABEL_769:
                        v416 = *(const char **)(v409 + 24LL * v411);
                        v4 = a1;
                        sqlite3VdbeError(
                          a1,
                          "cannot store %s value in %s column %s.%s",
                          off_18028E268[*((unsigned __int8 *)qword_1802E0640 + (v13 & 0x3F))],
                          off_180324C80[(unsigned int)(v5 - 1)],
                          *(const char **)v408,
                          v416);
                        v14 = 3091;
                        goto LABEL_1523;
                      }
                      goto LABEL_772;
                    case 3:
                    case 4:
                      v415 = (v13 & 4) == 0;
                      break;
                    case 5:
                      if ( (v13 & 4) != 0 )
                      {
                        v5 = 0xFFFFFFFFFFFFLL;
                        if ( (unsigned __int64)(*(_QWORD *)v410 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                        {
                          v414 = v13 | 8;
                          v13 = (unsigned __int16)v13 | 8u;
                          *(double *)v410 = (double)(int)*(_QWORD *)v410;
                        }
                        else
                        {
                          LOWORD(v13) = v13 | 0x20;
                          v414 = v13;
                        }
                        *v412 = v13;
                        *v412 = v414 & 0xFFFB;
                        goto LABEL_772;
                      }
                      v415 = (v13 & 0x28) == 0;
                      break;
                    case 6:
                      v413 = (v13 & 2) == 0;
                      goto LABEL_771;
                    default:
LABEL_772:
                      v410 += 56;
                      v3 = 0;
                      goto LABEL_773;
                  }
                  if ( v415 )
                    goto LABEL_769;
                  goto LABEL_772;
                }
                v14 = Table;
LABEL_977:
                v4 = a1;
                v7 = v835;
                goto LABEL_978;
              }
              v841 = 0;
              v857 = 0;
              v860 = 0;
              v417 = v4[15];
              v858 = 0;
              v859 = 0;
              v418 = *((_DWORD *)v6 + 2);
              v419 = *(_QWORD *)(v417 + 8LL * *((int *)v6 + 1));
LABEL_776:
              LODWORD(v840) = v418;
              while ( 1 )
              {
                v420 = *(unsigned int **)(v419 + 88);
                v421 = *((_DWORD *)v4 + 11);
                v837 = v420;
                if ( *(_DWORD *)(v419 + 32) == v421 )
                {
                  if ( !**(_BYTE **)(v419 + 48) )
                  {
                    v10 = 1;
LABEL_806:
                    v434 = (unsigned __int16 *)(v419 + 74);
                    if ( *(unsigned __int16 *)(v419 + 74) > v418 )
                    {
                      v447 = *(unsigned int *)(v419 + 4LL * v418 + 120);
                      v841 = *(_DWORD *)(v419 + 4LL * v418 + 120);
                      goto LABEL_849;
                    }
                    v431 = (int *)(v419 + 64);
                    if ( *(_DWORD *)(v419 + 64) >= *v420 )
                    {
                      v447 = 0;
                      v841 = 0;
                      goto LABEL_841;
                    }
                    v435 = *(_QWORD *)(v419 + 96);
                    v838 = v435;
                    if ( !v435 )
                    {
                      v857 = 0;
                      v858 = 0;
                      v860 = 0;
                      v859 = 0;
                      v438 = sqlite3VdbeMemFromBtreeZeroOffset(*(_QWORD *)(v419 + 48), *v420, &v857);
                      v3 = 0;
                      Table = v438;
                      v14 = v438;
                      if ( v438 )
                        goto LABEL_1546;
                      v435 = *((_QWORD *)&v857 + 1);
LABEL_811:
                      v838 = v435;
                    }
                    v439 = *v434;
                    v10 = 1;
                    v440 = (unsigned int)v840;
                    v441 = (unsigned __int8 *)(v435 + (unsigned int)*v431);
                    v442 = v420[v439];
                    v443 = v435 + *v420;
                    v444 = v837;
                    do
                    {
                      v841 = *v441;
                      *(_DWORD *)(v419 + 4LL * (int)v439 + 120) = v841;
                      if ( v841 >= 0x80 )
                      {
                        v441 += (unsigned __int8)sqlite3GetVarint32(v441, &v841);
                        *(_DWORD *)(v419 + 4LL * (int)v439 + 120) = v841;
                        if ( v841 < 0x80 )
                          v445 = *((unsigned __int8 *)qword_1802DD790 + v841);
                        else
                          v445 = (v841 - 12) >> 1;
                        v444 = v837;
                        v10 = 1;
                      }
                      else
                      {
                        ++v441;
                        v445 = *((unsigned __int8 *)qword_1802DD790 + (unsigned __int8)v841);
                      }
                      v442 += v445;
                      LODWORD(v439) = v439 + 1;
                      v444[(int)v439] = v442;
                    }
                    while ( (unsigned int)v439 <= v440 && (unsigned __int64)v441 < v443 );
                    v6 = (unsigned __int8 *)v848;
                    if ( (unsigned __int64)v441 < v443 )
                    {
                      if ( v442 <= *(unsigned int *)(v419 + 104) )
                        goto LABEL_824;
                    }
                    else if ( (unsigned __int64)v441 <= v443 && v442 == *(_DWORD *)(v419 + 104) )
                    {
LABEL_824:
                      v3 = 0;
                      goto LABEL_825;
                    }
                    v3 = 0;
                    if ( !*v444 )
                    {
                      LOWORD(v439) = 0;
                      LODWORD(v441) = v443;
LABEL_825:
                      v446 = (_DWORD)v441 - v838;
                      *(_WORD *)(v419 + 74) = v439;
                      *(_DWORD *)(v419 + 64) = v446;
                      if ( !*(_QWORD *)(v419 + 96) && ((WORD2(v858) & 0x9000) != 0 || (_DWORD)v859) )
                      {
                        vdbeMemClear(&v857);
                        v447 = v841;
                        v3 = 0;
                        v420 = v837;
                        v418 = (unsigned int)v840;
                        v10 = 1;
                      }
                      else
                      {
                        v447 = v841;
                        v420 = v837;
                        v418 = (unsigned int)v840;
                      }
LABEL_841:
                      if ( *(unsigned __int16 *)(v419 + 74) <= v418 )
                      {
                        v7 = v835;
                        v449 = v835 + 56LL * *((int *)v6 + 3);
                        if ( v6[1] == 0xF6 )
                        {
                          sqlite3VdbeMemShallowCopy(v835 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2), 0x2000);
                        }
                        else
                        {
                          if ( (*(_WORD *)(v449 + 20) & 0x9000) == 0 )
                          {
                            v14 = Table;
                            v4 = a1;
                            *(_WORD *)(v449 + 20) = 1;
                            goto LABEL_146;
                          }
                          vdbeMemClearExternAndSetNull(v835 + 56LL * *((int *)v6 + 3));
                        }
LABEL_844:
                        v14 = Table;
                        v4 = a1;
LABEL_422:
                        v9 = v831;
                        goto LABEL_244;
                      }
LABEL_849:
                      v7 = v835;
                      v450 = v835 + 56LL * *((int *)v6 + 3);
                      if ( (*(_WORD *)(v450 + 20) & 0x9000) != 0 )
                      {
                        vdbeMemClearExternAndSetNull(v835 + 56LL * *((int *)v6 + 3));
                        v447 = v841;
                      }
                      if ( *(_DWORD *)(v419 + 108) >= v420[v418 + 1] )
                      {
                        v451 = (const void *)(*(_QWORD *)(v419 + 96) + v420[v418]);
                        if ( (unsigned int)v447 < 0xC )
                        {
                          sqlite3VdbeSerialGet(*(_QWORD *)(v419 + 96) + v420[v418], v447, v450);
                          v14 = Table;
                          goto LABEL_854;
                        }
                        v452 = (unsigned int)(v447 - 12) >> 1;
                        *(_DWORD *)(v450 + 16) = v452;
                        *(_BYTE *)(v450 + 22) = v831;
                        v453 = (unsigned int)(v452 + 2);
                        if ( *(_DWORD *)(v450 + 32) >= (int)v453 )
                        {
                          *(_QWORD *)(v450 + 8) = *(_QWORD *)(v450 + 40);
                        }
                        else
                        {
                          v2 = v839;
                          if ( (int)v452 > *(_DWORD *)(v839 + 136) )
                            goto LABEL_1527;
                          *(_WORD *)(v450 + 20) = 1;
                          if ( (unsigned int)sqlite3VdbeMemGrow(v450, v453, 0) )
                          {
LABEL_858:
                            v4 = a1;
                            goto LABEL_1543;
                          }
                        }
                        memcpy_0(*(void **)(v450 + 8), v451, v452);
                        v14 = Table;
                        v3 = 0;
                        v4 = a1;
                        *(_BYTE *)(v452 + *(_QWORD *)(v450 + 8)) = 0;
                        v10 = 1;
                        *(_BYTE *)(v452 + *(_QWORD *)(v450 + 8) + 1) = 0;
                        *(_WORD *)(v450 + 20) = word_1802DDD48[v841 & 1];
                        goto LABEL_145;
                      }
                      *(_BYTE *)(v450 + 22) = v831;
                      v454 = v6[2] & 0xC0;
                      if ( v454 && (v454 == (char)0x80 || v841 >= 0xC && ((v841 & 1) == 0 || v454 == -64))
                        || (v841 < 0x80
                          ? (v455 = *((unsigned __int8 *)qword_1802DD790 + v841))
                          : (v455 = (v841 - 12) >> 1),
                            !v455) )
                      {
                        sqlite3VdbeSerialGet(&qword_1802DD340, v841, v450);
                        goto LABEL_844;
                      }
                      v4 = a1;
                      v456 = vdbeColumnFromOverflow(v419, v418, v841, v420[v418], *((_DWORD *)a1 + 11), v847, v450);
                      v3 = 0;
                      Table = v456;
                      v14 = v456;
                      if ( v456 )
                      {
                        if ( v456 != 7 )
                        {
                          if ( v456 != 18 )
                            goto LABEL_1546;
                          goto LABEL_1528;
                        }
                        goto LABEL_1542;
                      }
LABEL_80:
                      v9 = v831;
LABEL_52:
                      v5 = v834;
                      v10 = 1;
                      v13 = v832;
                      goto LABEL_53;
                    }
                    if ( !*(_QWORD *)(v419 + 96) && ((WORD2(v858) & 0x9000) != 0 || (_DWORD)v859) )
                    {
                      vdbeMemClear(&v857);
                      v3 = 0;
                      v10 = 1;
                    }
LABEL_836:
                    v5 = v834;
                    v448 = *(_DWORD *)(v834 + 12);
                    if ( v448 > 0 )
                    {
                      v14 = Table;
                      v4 = a1;
                      v6 = (unsigned __int8 *)(v834 + 24LL * (v448 - 1));
LABEL_838:
                      v7 = v835;
                      goto LABEL_147;
                    }
                    v14 = sqlite3CorruptError(96310);
LABEL_1522:
                    v4 = a1;
                    goto LABEL_1523;
                  }
                }
                else
                {
                  if ( *(_BYTE *)(v419 + 2) )
                  {
                    if ( *(_BYTE *)v419 == 3 && *(int *)(v419 + 36) > 0 )
                    {
                      v427 = (unsigned int *)(v419 + 108);
                      v429 = 56LL * *(int *)(v419 + 36);
                      v430 = *(_DWORD *)(v429 + v7 + 16);
                      *(_DWORD *)(v419 + 108) = v430;
                      *(_DWORD *)(v419 + 104) = v430;
                      Payload = *(unsigned __int8 **)(v429 + v7 + 8);
LABEL_793:
                      v431 = (int *)(v419 + 64);
                      *(_QWORD *)(v419 + 96) = Payload;
                      *(_DWORD *)(v419 + 32) = *((_DWORD *)a1 + 11);
                      v432 = *Payload;
                      *v420 = v432;
                      if ( v432 >= 0x80 )
                      {
                        LOBYTE(v433) = sqlite3GetVarint32(*(_QWORD *)(v419 + 96), v420);
                        v3 = 0;
                        v433 = (unsigned __int8)v433;
                        v10 = 1;
                      }
                      else
                      {
                        v10 = 1;
                        v433 = 1;
                      }
                      v434 = (unsigned __int16 *)(v419 + 74);
                      *v431 = v433;
                      *(_WORD *)(v419 + 74) = 0;
                      if ( *v427 >= *v420 )
                      {
                        v435 = *(_QWORD *)(v419 + 96);
                        goto LABEL_811;
                      }
                      *(_QWORD *)(v419 + 96) = 0;
                      *v427 = 0;
                      if ( *v420 <= 0x18003 && *v420 <= *(_DWORD *)(v419 + 104) )
                      {
                        v4 = a1;
                        goto LABEL_806;
                      }
                      goto LABEL_836;
                    }
                    v436 = v7 + 56LL * *((int *)v6 + 3);
                    if ( (*(_WORD *)(v436 + 20) & 0x9000) == 0 )
                    {
                      v14 = Table;
                      v10 = 1;
                      *(_WORD *)(v436 + 20) = 1;
                      goto LABEL_146;
                    }
                    v437 = v7 + 56LL * *((int *)v6 + 3);
LABEL_803:
                    vdbeMemClearExternAndSetNull(v437);
                    v14 = Table;
                    goto LABEL_422;
                  }
                  v422 = *(_QWORD *)(v419 + 48);
                  if ( *(_BYTE *)(v419 + 3) )
                  {
                    v423 = *(_QWORD *)(v419 + 16);
                    if ( !v423 || (v424 = *(_DWORD *)(v423 + 4LL * (v418 + 1))) == 0 )
                    {
                      v426 = sqlite3VdbeFinishMoveto(v419);
                      v3 = 0;
                      Table = v426;
                      if ( v426 )
                      {
LABEL_787:
                        v14 = Table;
                        goto LABEL_1546;
                      }
LABEL_789:
                      getCellInfo(v422);
                      v427 = (unsigned int *)(v419 + 108);
                      *(_DWORD *)(v419 + 104) = *(_DWORD *)(v422 + 64);
                      Payload = (unsigned __int8 *)fetchPayload(v422, v419 + 108);
                      v3 = 0;
                      goto LABEL_793;
                    }
                    v419 = *(_QWORD *)(v419 + 40);
                    v418 = v424 - 1;
                    goto LABEL_776;
                  }
                  if ( !*(_BYTE *)v422 )
                    goto LABEL_789;
                }
                v425 = sqlite3VdbeHandleMovedCursor(v419);
                v3 = 0;
                Table = v425;
                if ( v425 )
                  goto LABEL_787;
              }
            }
            v460 = v15 - 100;
            if ( !v460 )
            {
              v468 = *(_QWORD *)(v2 + 32);
              v469 = 32LL * *((int *)v6 + 1);
              updated = sqlite3BtreeUpdateMeta(
                          *(_QWORD *)(v469 + v468 + 8),
                          *((unsigned int *)v6 + 2),
                          *((unsigned int *)v6 + 3));
              v10 = 1;
              Table = updated;
              v14 = updated;
              if ( *((_DWORD *)v6 + 2) == 1 )
              {
                **(_DWORD **)(v469 + v468 + 24) = *((_DWORD *)v6 + 3) - *((unsigned __int16 *)v6 + 1);
                *(_DWORD *)(v2 + 44) |= 1u;
                sqlite3FkClearTriggerCache(v2, *((unsigned int *)v6 + 1));
                v10 = 1;
              }
              else if ( *((_DWORD *)v6 + 2) == 2 )
              {
                *(_BYTE *)(*(_QWORD *)(v469 + v468 + 24) + 112LL) = v6[12];
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
            v461 = v460 - 1;
            if ( v461 )
            {
              v462 = v461 - 1;
              if ( v462 && (unsigned int)(v462 - 1) > 1 )
                goto LABEL_53;
LABEL_880:
              v463 = v7 + 56LL * *((int *)v6 + 1);
              v464 = v7 + 56LL * *((int *)v6 + 2);
              v465 = 56LL * *((int *)v6 + 3) + v7;
              if ( ((unsigned __int8)(*(_BYTE *)(v463 + 20) | *(_BYTE *)(v464 + 20)) & (unsigned __int8)v10) != 0 )
              {
                if ( (*(_WORD *)(v465 + 20) & 0x9000) == 0 )
                {
                  *(_WORD *)(v465 + 20) = v10;
                  goto LABEL_838;
                }
                vdbeMemClearExternAndSetNull(v465);
                goto LABEL_421;
              }
              v472 = sqlite3VdbeIntValue(v464, v464);
              v474 = sqlite3VdbeIntValue(v463, v473);
              v475 = *v6;
              v476 = v474;
              if ( *v6 == 102 )
              {
                v472 &= v474;
LABEL_900:
                v3 = 0;
LABEL_915:
                *(_QWORD *)v465 = v472;
                *(_WORD *)(v465 + 20) &= 0xF244u;
                *(_WORD *)(v465 + 20) |= 4u;
LABEL_949:
                v7 = v835;
LABEL_950:
                v9 = v831;
                goto LABEL_951;
              }
              if ( v475 == 103 )
              {
                v472 |= v474;
                goto LABEL_900;
              }
              v3 = 0;
              if ( !v474 )
                goto LABEL_915;
              if ( v474 < 0 )
              {
                v475 = -47 - v475;
                if ( v474 <= -64 )
                  goto LABEL_906;
                v476 = -v474;
              }
              if ( v476 < 64 )
              {
                if ( v475 == 104 )
                {
                  v472 <<= v476;
                }
                else if ( v472 >= 0 )
                {
                  v472 = (unsigned __int64)v472 >> v476;
                }
                else
                {
                  v472 = ((unsigned __int64)v472 >> v476) | (-1LL << (64 - (unsigned __int8)v476));
                }
                goto LABEL_915;
              }
LABEL_906:
              if ( v472 >= 0 || v475 == 104 )
                v472 = 0;
              else
                v472 = -1;
              goto LABEL_915;
            }
            v466 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( v466 && *(_DWORD *)(v466 + 68) == *((_DWORD *)v6 + 2) )
            {
              v467 = *(_QWORD *)(v466 + 48);
              sqlite3_free(*(_QWORD *)(v467 + 24));
              v3 = 0;
              *(_QWORD *)(v467 + 24) = 0;
              v10 = 1;
              *(_BYTE *)v467 = 1;
LABEL_1026:
              *(_BYTE *)(*(_QWORD *)(v466 + 48) + 3LL) = v6[2] & 3;
              goto LABEL_173;
            }
            goto LABEL_1013;
          }
          if ( (unsigned int)v15 > 0x6F )
          {
            v512 = v15 - 112;
            if ( v512 )
            {
              v513 = v512 - 1;
              if ( v513 )
              {
                v514 = v513 - 1;
                if ( !v514 )
                {
                  v518 = v7 + 56LL * *((int *)v6 + 1);
                  v519 = v7 + 56LL * *((int *)v6 + 2);
                  if ( (*(_WORD *)(v519 + 20) & 0x9000) != 0 )
                  {
                    vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 2));
                    v13 = v832;
                    v3 = 0;
                    v10 = 1;
                  }
                  else
                  {
                    *(_WORD *)(v519 + 20) = v10;
                  }
                  if ( ((unsigned __int8)v10 & *(_BYTE *)(v518 + 20)) == 0 )
                  {
                    *(_WORD *)(v519 + 20) = 4;
                    *(_QWORD *)v519 = ~sqlite3VdbeIntValue(v518, v13);
                    goto LABEL_422;
                  }
                  goto LABEL_623;
                }
                if ( v514 != 1 )
                  goto LABEL_53;
                v515 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2));
                Cursor = allocateCursor(v4, *((unsigned int *)v6 + 1), (unsigned int)*(__int16 *)(v515 + 72), 0);
                if ( Cursor )
                {
                  *(_DWORD *)(Cursor + 8) |= 1u;
                  *(_BYTE *)(Cursor + 2) = 1;
                  *(_QWORD *)(Cursor + 56) = *(_QWORD *)(v515 + 56);
                  *(_BYTE *)(Cursor + 4) = *(_BYTE *)(v515 + 4);
                  *(_DWORD *)(Cursor + 68) = *(_DWORD *)(v515 + 68);
                  v517 = *(_DWORD *)(Cursor + 8) ^ (*(_DWORD *)(v515 + 8) ^ *(_DWORD *)(Cursor + 8)) & 4;
                  *(_DWORD *)(Cursor + 8) = v517;
                  *(_QWORD *)(Cursor + 16) = *(_QWORD *)(v515 + 16);
                  *(_DWORD *)(Cursor + 8) = v517 | 8;
                  *(_DWORD *)(v515 + 8) |= 8u;
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
            v520 = *((_DWORD *)v6 + 3);
            v521 = *(_QWORD *)(v2 + 32);
            v522 = *((unsigned int *)v6 + 2);
            v523 = 32LL * v520;
            v524 = *(_QWORD *)(v523 + v521 + 8);
            if ( *v6 == 113 )
            {
              v525 = *((_WORD *)v6 + 1) & 8 | 4;
              v526 = *(_BYTE *)(*(_QWORD *)(v523 + v521 + 24) + 112LL);
              if ( v526 < *((_BYTE *)a1 + 197) )
                *((_BYTE *)a1 + 197) = v526;
            }
            else
            {
              v525 = 0;
            }
            if ( (v6[2] & 0x10) != 0 )
            {
              sqlite3VdbeMemIntegerify(v835 + 56 * v522);
              LODWORD(v522) = *(_DWORD *)(v835 + 56 * v522);
            }
            v527 = v6[1];
            if ( v527 == 0xF8 )
            {
              v528 = *((_QWORD *)v6 + 2);
              v529 = *(unsigned __int16 *)(v528 + 8);
            }
            else
            {
              v529 = 0;
              v528 = 0;
              if ( v527 == 0xFD )
                v529 = *((unsigned int *)v6 + 4);
            }
            v530 = allocateCursor(a1, *((unsigned int *)v6 + 1), v529, 0);
            v466 = v530;
            if ( v530 )
            {
              v531 = *(_QWORD *)(v530 + 48);
              *(_DWORD *)(v530 + 8) |= 4u;
              *(_BYTE *)(v530 + 1) = v520;
              *(_BYTE *)(v530 + 2) = 1;
              *(_DWORD *)(v530 + 68) = v522;
              v532 = sqlite3BtreeCursor(v524, v522, v525, v528, v531);
              v4 = a1;
              v14 = v532;
              v7 = v835;
              *(_QWORD *)(v466 + 56) = v528;
              Table = v532;
              v3 = 0;
              *(_BYTE *)(v466 + 4) = v6[1] != 0xF8;
              v10 = 1;
              goto LABEL_1026;
            }
LABEL_1541:
            v4 = a1;
            goto LABEL_1542;
          }
          if ( (_DWORD)v15 != 111 )
          {
            v477 = v15 - 106;
            if ( v477 )
            {
              v478 = v477 - 1;
              if ( v478 )
              {
                v479 = v478 - 1;
                if ( v479 )
                {
                  if ( (unsigned int)(v479 - 1) > 1 )
                    goto LABEL_53;
                }
              }
            }
            v480 = *((int *)v6 + 3);
            v481 = v7 + 56LL * *((int *)v6 + 1);
            v482 = 56LL * *((int *)v6 + 2) + v7;
            v850 = 0;
            v483 = v835 + 56 * v480;
            v484 = *(_WORD *)(v482 + 20);
            if ( (*(_BYTE *)(v481 + 20) & (unsigned __int8)v484 & 4) == 0 )
            {
              if ( ((unsigned __int8)(*(_BYTE *)(v481 + 20) | v484) & (unsigned __int8)v10) != 0 )
              {
LABEL_973:
                if ( (*(_WORD *)(v483 + 20) & 0x9000) == 0 )
                {
                  v10 = 1;
                  *(_WORD *)(v483 + 20) = 1;
LABEL_976:
                  v13 = v832;
                  goto LABEL_977;
                }
                vdbeMemClearExternAndSetNull(v483);
LABEL_854:
                v4 = a1;
                goto LABEL_421;
              }
              v485 = numericType(v481);
              if ( (v485 & (unsigned __int8)numericType(v482) & 4) == 0 )
                goto LABEL_955;
              v3 = 0;
              v10 = 1;
            }
            v486 = *v6;
            v487 = *(_QWORD *)v482;
            v488 = *(_QWORD *)v481;
            v850 = *(_QWORD *)v482;
            v489 = v486 - 106;
            if ( !v489 )
            {
              if ( v488 < 0 )
              {
                if ( v487 < 0 && (__int64)(0x8000000000000001uLL - v487) > v488 + 1 )
                  goto LABEL_955;
              }
              else if ( v487 > 0 && 0x7FFFFFFFFFFFFFFFLL - v487 < v488 )
              {
                goto LABEL_955;
              }
              v493 = v487 + v488;
              goto LABEL_946;
            }
            v490 = v489 - 1;
            if ( v490 )
            {
              v491 = v490 - 1;
              if ( v491 )
              {
                if ( v491 != 1 )
                {
                  if ( v488 )
                  {
                    v492 = v487;
                    if ( v488 == -1 )
                      v488 = v10;
                    v850 = v492 % v488;
                    goto LABEL_947;
                  }
                  goto LABEL_972;
                }
                if ( !v488 )
                  goto LABEL_972;
                if ( v488 != -1 || v487 != 0x8000000000000000uLL )
                {
                  v493 = v487 / v488;
LABEL_946:
                  v850 = v493;
LABEL_947:
                  *(_QWORD *)v483 = v850;
                  v495 = *(_WORD *)(v483 + 20) & 0xF240 | 4;
LABEL_948:
                  *(_WORD *)(v483 + 20) = v495;
                  v4 = a1;
                  goto LABEL_949;
                }
LABEL_955:
                v496 = sqlite3VdbeRealValue(v481);
                v498 = sqlite3VdbeRealValue(v482);
                switch ( *v6 )
                {
                  case 'j':
                    v502 = v498 + v496;
                    break;
                  case 'k':
                    v502 = v498 - v496;
                    break;
                  case 'l':
                    v502 = v498 * v496;
                    break;
                  case 'm':
                    if ( v496 == 0.0 )
                    {
                      v3 = 0;
                      goto LABEL_972;
                    }
                    v502 = v498 / v496;
                    break;
                  default:
                    v499 = sqlite3VdbeIntValue(v481, v497);
                    v501 = sqlite3VdbeIntValue(v482, v500);
                    v3 = 0;
                    v850 = v501;
                    if ( v499 )
                    {
                      if ( v499 == -1 )
                        v499 = 1;
                      v502 = (double)(int)(v501 % v499);
LABEL_969:
                      if ( (*(_QWORD *)&v502 & 0xFFFFFFFFFFFFFLL) == 0
                        || (*(_QWORD *)&v502 & 0x7FF0000000000000LL) != 0x7FF0000000000000LL )
                      {
                        v503 = *(_WORD *)(v483 + 20);
                        *(double *)v483 = v502;
                        v495 = v503 & 0xF240 | 8;
                        goto LABEL_948;
                      }
                    }
LABEL_972:
                    v5 = v834;
                    goto LABEL_973;
                }
                v3 = 0;
                goto LABEL_969;
              }
              v494 = sqlite3MulInt64(&v850, v488);
            }
            else
            {
              v494 = sqlite3SubInt64(&v850, v488);
            }
            v3 = 0;
            if ( !v494 )
              goto LABEL_947;
            goto LABEL_955;
          }
          v504 = v7 + 56LL * *((int *)v6 + 1);
          v505 = *(_WORD *)(v504 + 20);
          v506 = v7 + 56LL * *((int *)v6 + 2);
          v507 = v7 + 56LL * *((int *)v6 + 3);
          if ( ((unsigned __int8)(*(_BYTE *)(v506 + 20) | v505) & (unsigned __int8)v10) != 0 )
          {
            if ( (*(_WORD *)(v507 + 20) & 0x9000) == 0 )
            {
              v14 = Table;
              *(_WORD *)(v507 + 20) = v10;
              goto LABEL_148;
            }
            v437 = v7 + 56LL * *((int *)v6 + 3);
            goto LABEL_803;
          }
          if ( (v505 & 0x12) != 0 )
          {
            if ( (v505 & 0x400) == 0 )
              goto LABEL_989;
            v508 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 1));
          }
          else
          {
            LOBYTE(v13) = v831;
            v508 = sqlite3VdbeMemStringify(v7 + 56LL * *((int *)v6 + 1), v13, 0);
          }
          if ( v508 )
            goto LABEL_1542;
          v505 = *(_WORD *)(v504 + 20) & 0xFFFD;
LABEL_989:
          v509 = *(_WORD *)(v506 + 20);
          if ( (v509 & 0x12) != 0 )
          {
            if ( (v509 & 0x400) == 0 )
              goto LABEL_995;
            v510 = sqlite3VdbeMemExpandBlob(v506);
          }
          else
          {
            LOBYTE(v13) = v831;
            v510 = sqlite3VdbeMemStringify(v506, v13, 0);
          }
          if ( !v510 )
          {
            v509 = *(_WORD *)(v506 + 20) & 0xFFFD;
LABEL_995:
            LODWORD(v511) = *(_DWORD *)(v504 + 16) + *(_DWORD *)(v506 + 16);
            if ( (int)v511 > *(_DWORD *)(v839 + 136) )
              goto LABEL_1527;
            if ( !(unsigned int)sqlite3VdbeMemGrow(v507, (unsigned int)(v511 + 2), v507 == v506) )
            {
              v511 = (int)v511;
              *(_WORD *)(v507 + 20) &= 0xF242u;
              *(_WORD *)(v507 + 20) |= 2u;
              if ( v507 != v506 )
              {
                memcpy_0(*(void **)(v507 + 8), *(const void **)(v506 + 8), *(int *)(v506 + 16));
                *(_WORD *)(v506 + 20) = v509;
              }
              memcpy_0(
                (void *)(*(_QWORD *)(v507 + 8) + *(int *)(v506 + 16)),
                *(const void **)(v504 + 8),
                *(int *)(v504 + 16));
              v9 = v831;
              v10 = 1;
              *(_WORD *)(v504 + 20) = v505;
              if ( v831 > 1u )
                v511 = (int)v511 & 0xFFFFFFFFFFFFFFFEuLL;
              v3 = 0;
              v14 = Table;
              *(_BYTE *)(v511 + *(_QWORD *)(v507 + 8)) = 0;
              *(_BYTE *)(*(_QWORD *)(v507 + 8) + v511 + 1) = 0;
              *(_WORD *)(v507 + 20) |= 0x200u;
              *(_DWORD *)(v507 + 16) = v511;
              v4 = a1;
              *(_BYTE *)(v507 + 22) = v831;
              goto LABEL_335;
            }
            goto LABEL_1541;
          }
LABEL_1542:
          v2 = v839;
          goto LABEL_1543;
        }
LABEL_1042:
        if ( *((int *)v6 + 3) > 0 )
        {
          *(_DWORD *)(56LL * *((int *)v6 + 3) + v7 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v6 + 3) + v7 + 8) = Src;
        }
        v541 = *((int *)v6 + 1);
        v542 = *(_QWORD *)(v4[15] + 8 * v541);
        if ( !v542 || (*(_BYTE *)(v542 + 8) & 8) != 0 || *((_DWORD *)v6 + 2) > *(__int16 *)(v542 + 72) )
        {
          v546 = allocateCursor(v4, v541, *((unsigned int *)v6 + 2), 0);
          v542 = v546;
          if ( !v546 )
            goto LABEL_1543;
          v547 = (_QWORD *)(v546 + 16);
          *(_DWORD *)(v546 + 8) |= 1u;
          LODWORD(v830) = *((unsigned __int16 *)v6 + 1) | 5;
          v548 = sqlite3BtreeOpen(*(_QWORD *)v2, 0, v2, v546 + 16, v830, 1054);
          v3 = 0;
          v14 = v548;
          if ( v548 )
            goto LABEL_1545;
          v549 = sqlite3BtreeBeginTrans(*v547, 1, 0);
          v3 = 0;
          Table = v549;
          v14 = v549;
          if ( !v549 )
          {
            v550 = *((_QWORD *)v6 + 2);
            v551 = (_DWORD *)(v542 + 68);
            *(_QWORD *)(v542 + 56) = v550;
            if ( v550 )
            {
              v552 = *v547;
              v553 = *((unsigned __int16 *)v6 + 1) | 2;
              sqlite3BtreeEnter(*v547);
              Table = btreeCreateTable(v552, v542 + 68, v553);
              sqlite3BtreeLeave(v552);
              v3 = 0;
              if ( Table )
              {
                v14 = Table;
              }
              else
              {
                v14 = sqlite3BtreeCursor(*v547, *v551, 4, v550, *(_QWORD *)(v542 + 48));
                Table = v14;
                v3 = 0;
              }
              v9 = v831;
              *(_BYTE *)(v542 + 4) = 0;
            }
            else
            {
              v554 = *(_QWORD *)(v542 + 48);
              v555 = *v547;
              *v551 = 1;
              v14 = sqlite3BtreeCursor(v555, 1, 4, 0, v554);
              Table = v14;
              v3 = 0;
              *(_BYTE *)(v542 + 4) = 1;
            }
          }
          *(_DWORD *)(v542 + 8) = *(_DWORD *)(v542 + 8) & 0xFFFFFFFB | (*((_WORD *)v6 + 1) != 8 ? 4 : 0);
          if ( v14 )
          {
            sqlite3BtreeClose(*(_QWORD *)(v542 + 16));
            goto LABEL_1522;
          }
          v4 = a1;
        }
        else
        {
          v543 = *(unsigned int *)(v542 + 68);
          v544 = *(_QWORD *)(v542 + 16);
          *(_QWORD *)(v542 + 24) = 0;
          *(_DWORD *)(v542 + 32) = 0;
          v545 = sqlite3BtreeClearTable(v544, v543, 0);
          v3 = 0;
          Table = v545;
          v14 = v545;
          if ( v545 )
            goto LABEL_1546;
        }
        v10 = 1;
        *(_BYTE *)(v542 + 2) = 1;
        goto LABEL_335;
      }
      if ( (unsigned int)v15 <= 0x81 )
      {
        if ( (_DWORD)v15 == 129 )
        {
          if ( *((_DWORD *)v6 + 3) )
            v603 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
          else
            v603 = 0;
          v75 = sqlite3BtreeTransferRow(
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL),
                  *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 2)) + 48LL),
                  v603);
          goto LABEL_153;
        }
        if ( (unsigned int)v15 <= 0x7A )
        {
          if ( (_DWORD)v15 == 122 )
          {
            if ( *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) )
            {
              sqlite3VdbeFreeCursorNN(v4);
              v5 = v834;
              v3 = 0;
              v10 = 1;
            }
            *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) = 0;
            goto LABEL_196;
          }
          v533 = v15 - 117;
          if ( !v533 )
          {
            v556 = out2Prerelease(v4, v6);
            v558 = *((_QWORD *)v6 + 2);
            v559 = v556;
            if ( v558 )
            {
              v561 = -1;
              do
                ++v561;
              while ( *(_BYTE *)(v558 + v561) );
              v560 = v561 & 0x3FFFFFFF;
            }
            else
            {
              v560 = 0;
            }
            *((_DWORD *)v6 + 1) = v560;
            if ( v9 != 1 )
            {
              LOBYTE(v557) = 1;
              Table = sqlite3VdbeMemSetStr(v556, v558, -1, v557, 0);
              v14 = Table;
              if ( Table )
                goto LABEL_1528;
              if ( (unsigned int)sqlite3VdbeChangeEncoding(v559, v9) )
                goto LABEL_1543;
              *(_DWORD *)(v559 + 32) = 0;
              *(_WORD *)(v559 + 20) |= 0x2000u;
              if ( v6[1] == 0xFA )
              {
                v562 = *((_QWORD *)v6 + 2);
                if ( v562 )
                  sqlite3DbFreeNN(v2, v562);
              }
              v6[1] = -6;
              *((_QWORD *)v6 + 2) = *(_QWORD *)(v559 + 8);
              v560 = *(_DWORD *)(v559 + 16);
              *((_DWORD *)v6 + 1) = v560;
            }
            if ( v560 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            *v6 = 73;
LABEL_1075:
            v563 = out2Prerelease(v4, v6);
            v3 = 0;
            *(_WORD *)(v563 + 20) = 8706;
            *(_QWORD *)(v563 + 8) = *((_QWORD *)v6 + 2);
            *(_DWORD *)(v563 + 16) = *((_DWORD *)v6 + 1);
            *(_BYTE *)(v563 + 22) = v9;
            if ( *((int *)v6 + 3) <= 0 )
            {
LABEL_1408:
              v10 = 1;
              goto LABEL_1404;
            }
            v10 = 1;
            v13 = v832;
            if ( *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) == *((unsigned __int16 *)v6 + 1) )
            {
              *(_WORD *)(v563 + 20) = 8720;
              goto LABEL_1078;
            }
            goto LABEL_623;
          }
          v534 = v533 - 1;
          if ( v534 )
          {
            v535 = v534 - 1;
            if ( v535 )
            {
              v536 = v535 - 1;
              if ( v536 )
              {
                if ( v536 != 1 )
                  goto LABEL_53;
                LOBYTE(v16) = 3;
                v537 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 3), v16);
                v3 = 0;
                if ( !v537 )
                  goto LABEL_1543;
                v10 = 1;
                *(_BYTE *)(v537 + 2) = 1;
                *(_DWORD *)(v537 + 36) = *((_DWORD *)v6 + 2);
                *(_QWORD *)(v537 + 48) = &dword_180335544;
                *(_BYTE *)(v537 + 4) = 1;
                goto LABEL_195;
              }
              v538 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
              v539 = *(_QWORD *)(v538 + 24);
              *(_QWORD *)(v538 + 24) = v539 + 1;
              if ( v539 )
                goto LABEL_196;
              goto LABEL_1219;
            }
            LOBYTE(v16) = v10;
            v540 = allocateCursor(v4, *((unsigned int *)v6 + 1), *((unsigned int *)v6 + 2), v16);
            if ( !v540 )
              goto LABEL_1543;
            *(_QWORD *)(v540 + 56) = *((_QWORD *)v6 + 2);
            v75 = sqlite3VdbeSorterInit(v2, *((unsigned int *)v6 + 3), v540);
            goto LABEL_153;
          }
          goto LABEL_1042;
        }
        v564 = v15 - 124;
        if ( !v564 )
        {
          v594 = *((int *)v6 + 7);
          *(_QWORD *)&v846 = 0;
          v595 = v4[15];
          LODWORD(v838) = 0;
          v844 = 0;
          v845 = 0;
          v596 = *(_QWORD *)(v595 + 8 * v594);
          if ( **(_BYTE **)(v596 + 48) )
            goto LABEL_53;
          v597 = *((_DWORD *)v6 + 1);
          *(_QWORD *)&v844 = *(_QWORD *)(v596 + 56);
          WORD6(v845) = *((_WORD *)v6 + 20);
          v598 = *((int *)v6 + 9);
          BYTE14(v845) = 0;
          *((_QWORD *)&v844 + 1) = v7 + 56 * v598;
          while ( 1 )
          {
            v599 = sqlite3VdbeIdxKeyCompare(v2, v596, &v844, &v838);
            v3 = 0;
            Table = v599;
            v14 = v599;
            if ( v599 )
              goto LABEL_1546;
            v600 = (int)v838 < 0;
            if ( (int)v838 > 0 )
            {
              if ( !*((_WORD *)v6 + 1) )
                goto LABEL_1149;
              v600 = (int)v838 < 0;
            }
            if ( !v600 )
              goto LABEL_1218;
            if ( v597 <= 0 )
              goto LABEL_1408;
            v601 = *(_QWORD *)(v596 + 48);
            *(_DWORD *)(v596 + 32) = 0;
            v602 = sqlite3BtreeNext(v601, 0);
            v3 = 0;
            v14 = v602;
            if ( v602 )
              break;
            --v597;
          }
          if ( v602 != 101 )
            goto LABEL_1546;
          v14 = 0;
          Table = 0;
LABEL_1149:
          v9 = v831;
          v6 += 24;
          goto LABEL_213;
        }
        v565 = v564 - 1;
        if ( !v565 )
        {
          v592 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v593 = *(unsigned __int16 *)(v592 + 12);
          if ( v593 >= *((_DWORD *)v6 + 2) )
          {
            if ( v593 > *((_DWORD *)v6 + 3) )
              *(_WORD *)(v592 + 12) = *((_WORD *)v6 + 6);
            v13 = v832;
            goto LABEL_53;
          }
          *(_WORD *)(v592 + 12) = *((_WORD *)v6 + 4);
LABEL_196:
          v13 = v832;
          goto LABEL_53;
        }
        v566 = v565 - 1;
        if ( !v566 )
        {
          v590 = (_QWORD *)out2Prerelease(v4, v6);
          v10 = 1;
          *v590 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 24LL);
          v591 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          ++*(_QWORD *)(v591 + 24);
          goto LABEL_60;
        }
        v567 = v566 - 1;
        if ( !v567 )
        {
          v838 = 0;
          LODWORD(v840) = 0;
          v581 = (__int64 *)out2Prerelease(v4, v6);
          v582 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( (*(_BYTE *)(v582 + 8) & 2) != 0 )
          {
            v3 = 0;
          }
          else
          {
            v583 = sqlite3BtreeLast(*(_QWORD *)(v582 + 48), &v840);
            v3 = 0;
            Table = v583;
            v14 = v583;
            if ( v583 )
              goto LABEL_1546;
            if ( (_DWORD)v840 )
            {
              v838 = 1;
            }
            else
            {
              v584 = sqlite3BtreeIntegerKey(*(_QWORD *)(v582 + 48));
              v838 = v584;
              if ( v584 == 0x7FFFFFFFFFFFFFFFLL )
                *(_DWORD *)(v582 + 8) |= 2u;
              else
                v838 = v584 + 1;
              v3 = 0;
            }
          }
          if ( *((_DWORD *)v6 + 3) )
          {
            v585 = v4[33];
            if ( v585 )
            {
              while ( *(_QWORD *)(v585 + 8) )
                v585 = *(_QWORD *)(v585 + 8);
              v586 = (__int64 *)(*(_QWORD *)(v585 + 24) + 56LL * *((int *)v6 + 3));
            }
            else
            {
              v586 = (__int64 *)(v835 + 56LL * *((int *)v6 + 3));
            }
            sqlite3VdbeMemIntegerify(v586);
            if ( *v586 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v582 + 8) & 2) != 0 )
            {
              v14 = 13;
              goto LABEL_1523;
            }
            v587 = v838;
            if ( v838 < *v586 + 1 )
            {
              v587 = *v586 + 1;
              v838 = v587;
            }
            *v586 = v587;
            v3 = 0;
          }
          if ( (*(_BYTE *)(v582 + 8) & 2) != 0 )
          {
            v588 = 0;
            while ( 1 )
            {
              sqlite3_randomness(8, &v838);
              v838 = (v838 & 0x3FFFFFFFFFFFFFFFLL) + 1;
              v589 = sqlite3BtreeTableMoveto(*(_QWORD *)(v582 + 48), v838, 0, &v840);
              v3 = 0;
              Table = v589;
              v14 = v589;
              if ( v589 )
                goto LABEL_1546;
              if ( (_DWORD)v840 )
                break;
              if ( ++v588 >= 100 )
              {
                v14 = 13;
                goto LABEL_1546;
              }
            }
          }
          *(_BYTE *)(v582 + 3) = 0;
          *(_DWORD *)(v582 + 32) = 0;
          *v581 = v838;
          goto LABEL_79;
        }
        if ( v567 != 1 )
          goto LABEL_53;
        v568 = *((int *)v6 + 1);
        v569 = 56LL * *((int *)v6 + 2);
        v844 = 0;
        v845 = 0;
        v570 = v4[15];
        v846 = 0;
        v571 = *(_QWORD *)(v570 + 8 * v568);
        v76 = v6[1] == 0xFB;
        v572 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
        *((_QWORD *)&v844 + 1) = v572;
        if ( v76 && *(_QWORD *)(v2 + 320) )
        {
          v573 = *((_QWORD *)v6 + 2);
          v574 = *(_QWORD *)(32LL * *(char *)(v571 + 1) + *(_QWORD *)(v2 + 32));
        }
        else
        {
          v573 = 0;
          v574 = 0;
        }
        if ( ((unsigned __int8)v10 & v6[2]) != 0 )
        {
          v4[7] += v10;
          if ( (v6[2] & 0x20) != 0 )
            *(_QWORD *)(v2 + 56) = v572;
        }
        v575 = *((_WORD *)v6 + 1);
        *(_QWORD *)&v845 = *(_QWORD *)(v569 + v835 + 8);
        DWORD1(v846) = *(_DWORD *)(v569 + v835 + 16);
        if ( (v575 & 0x10) != 0 )
          v576 = *(unsigned int *)(v571 + 36);
        else
          v576 = 0;
        if ( (*(_WORD *)(v569 + v835 + 20) & 0x400) != 0 )
          DWORD2(v846) = *(_DWORD *)(v569 + v835);
        else
          DWORD2(v846) = 0;
        *(_QWORD *)&v844 = 0;
        v577 = sqlite3BtreeInsert(*(_QWORD *)(v571 + 48), &v844, (unsigned __int8)v575 & 0x8A, v576);
        v3 = 0;
        Table = v577;
        *(_BYTE *)(v571 + 3) = 0;
        v14 = v577;
        *(_DWORD *)(v571 + 32) = 0;
        if ( v577 )
          goto LABEL_1546;
        v10 = 1;
        ++v847;
        if ( !v573 )
          goto LABEL_1403;
        v578 = *((_QWORD *)&v844 + 1);
        v579 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64))(v2 + 320);
        v580 = (v6[2] & 4) != 0 ? 23 : 18;
LABEL_1103:
        v579(*(_QWORD *)(v2 + 312), v580, v574, *(_QWORD *)v573, v578);
        goto LABEL_421;
      }
      if ( (unsigned int)v15 > 0x87 )
      {
        switch ( (_DWORD)v15 )
        {
          case 0x88:
            v650 = *((int *)v6 + 1);
            v651 = *(_QWORD *)(v4[15] + 8 * v650);
            if ( !v651 )
            {
              LOBYTE(v16) = 3;
              v651 = allocateCursor(v4, v650, (unsigned int)v10, v16);
              if ( !v651 )
                goto LABEL_1543;
              *(_DWORD *)(v651 + 8) |= 8u;
              *(_DWORD *)(v651 + 36) = 0;
              *(_BYTE *)(v651 + 4) = 1;
              valid = sqlite3BtreeFakeValidCursor();
              v3 = 0;
              *(_QWORD *)(v651 + 48) = valid;
              v10 = 1;
            }
            *(_BYTE *)(v651 + 2) = v10;
            *(_DWORD *)(v651 + 32) = 0;
            if ( !*(_BYTE *)v651 )
            {
              sqlite3BtreeClearCursor(*(_QWORD *)(v651 + 48));
              goto LABEL_244;
            }
            goto LABEL_1404;
          case 0x89:
            goto LABEL_1211;
          case 0x8A:
            v635 = v4[15];
            v636 = *((int *)v6 + 1);
            v844 = 0;
            v845 = 0;
            v846 = 0;
            v637 = *(_QWORD *)(v635 + 8 * v636);
            v638 = v7 + 56LL * *((int *)v6 + 2);
            if ( ((unsigned __int8)v10 & v6[2]) != 0 )
              v4[7] += v10;
            if ( (*(_WORD *)(v638 + 20) & 0x400) != 0 )
            {
              v639 = sqlite3VdbeMemExpandBlob(v638);
              v3 = 0;
              v14 = v639;
              if ( v639 )
                goto LABEL_1546;
            }
            v640 = *((_WORD *)v6 + 1);
            *((_QWORD *)&v844 + 1) = *(int *)(v638 + 16);
            *(_QWORD *)&v844 = *(_QWORD *)(v638 + 8);
            v641 = v7 + 56LL * *((int *)v6 + 3);
            LOWORD(v846) = *((_WORD *)v6 + 8);
            *((_QWORD *)&v845 + 1) = v641;
            if ( (v640 & 0x10) != 0 )
              v642 = *(unsigned int *)(v637 + 36);
            else
              v642 = 0;
            v634 = sqlite3BtreeInsert(*(_QWORD *)(v637 + 48), &v844, (unsigned __int8)v640 & 0x8A, v642);
            v3 = 0;
            *(_DWORD *)(v637 + 32) = 0;
            break;
          default:
            v631 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v632 = v7 + 56LL * *((int *)v6 + 2);
            if ( (*(_WORD *)(v632 + 20) & 0x400) != 0 )
            {
              v633 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              v14 = v633;
              if ( v633 )
                goto LABEL_1546;
            }
            v634 = sqlite3VdbeSorterWrite(v631, v632);
            v3 = 0;
            break;
        }
        Table = v634;
        v14 = v634;
        v174 = v634 == 0;
LABEL_326:
        if ( !v174 )
          goto LABEL_1546;
        goto LABEL_80;
      }
      if ( (_DWORD)v15 != 135 )
      {
        v604 = v15 - 130;
        if ( v604 )
        {
          v605 = v604 - 1;
          if ( !v605 )
          {
            sqlite3VdbeSetChanges(v2, v4[7]);
            v3 = 0;
            v4[7] = 0;
            goto LABEL_52;
          }
          v606 = v605 - 1;
          if ( v606 )
          {
            v607 = v606 - 1;
            if ( !v607 )
            {
              v613 = sqlite3VdbeSorterRowkey(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)), v7 + 56LL * *((int *)v6 + 2));
              v3 = 0;
              Table = v613;
              v14 = v613;
              if ( v613 )
                goto LABEL_1546;
              *(_DWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3)) + 32LL) = 0;
              goto LABEL_52;
            }
            if ( v607 != 1 )
              goto LABEL_53;
            v608 = out2Prerelease(v4, v6);
            v609 = *(_QWORD *)(*(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1)) + 48LL);
            v610 = sqlite3BtreePayloadSize(v609);
            if ( v610 > *(_DWORD *)(v2 + 136) )
              goto LABEL_1528;
            v611 = sqlite3VdbeMemFromBtreeZeroOffset(v609, v610, v608);
            v3 = 0;
            Table = v611;
            v14 = v611;
            if ( v611 )
              goto LABEL_1546;
            if ( !*((_DWORD *)v6 + 3) && (*(_WORD *)(v608 + 20) & 0x4000) != 0 )
            {
              Writeable = sqlite3VdbeMemMakeWriteable(v608);
              v3 = 0;
              if ( Writeable )
                goto LABEL_1543;
              goto LABEL_80;
            }
            goto LABEL_1408;
          }
          v614 = v4[15];
          v615 = *((unsigned int *)v6 + 4);
          v616 = 56LL * *((int *)v6 + 3);
          v617 = *((int *)v6 + 1);
          LODWORD(v838) = 0;
          v618 = sqlite3VdbeSorterCompare(*(_QWORD *)(v614 + 8 * v617), v7 + v616, v615, &v838);
          v3 = 0;
          Table = v618;
          v14 = v618;
          if ( v618 )
            goto LABEL_1546;
          v109 = (_DWORD)v838 == 0;
          goto LABEL_194;
        }
        v619 = *((_DWORD *)v6 + 2);
        v620 = *(_QWORD *)(a1[15] + 8LL * *((int *)v6 + 1));
        if ( v6[1] == 0xFB && *(_QWORD *)(v2 + 320) )
        {
          v573 = *((_QWORD *)v6 + 2);
          v574 = *(_QWORD *)(32LL * *(char *)(v620 + 1) + *(_QWORD *)(v2 + 32));
          if ( (v6[2] & 2) != 0 && *(_BYTE *)(v620 + 4) )
            *(_QWORD *)(v620 + 80) = sqlite3BtreeIntegerKey(*(_QWORD *)(v620 + 48));
        }
        else
        {
          v574 = 0;
          v573 = 0;
        }
        LOBYTE(v13) = v6[2];
        v621 = sqlite3BtreeDelete(*(_QWORD *)(v620 + 48), v13);
        v3 = 0;
        Table = v621;
        *(_QWORD *)(v620 + 32) = 0;
        v14 = v621;
        if ( v621 )
          goto LABEL_1545;
        v10 = 1;
        ++v847;
        v76 = (v619 & 1) == 0;
        v4 = a1;
        if ( v76 )
          goto LABEL_1403;
        ++a1[7];
        v579 = *(void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64))(v2 + 320);
        if ( !v579 || !v573 || *(char *)(v573 + 48) < 0 )
          goto LABEL_1403;
        v578 = *(_QWORD *)(v620 + 80);
        v580 = v14 + 9;
        goto LABEL_1103;
      }
      v848 = 0;
      v622 = out2Prerelease(v4, v6);
      v623 = *((int *)v6 + 1);
      v3 = 0;
      v624 = v4[15];
      v625 = v622;
      v626 = *(_QWORD *)(v624 + 8 * v623);
      if ( *(_BYTE *)(v626 + 2) )
      {
        v10 = 1;
        *(_WORD *)(v622 + 20) = 1;
        goto LABEL_146;
      }
      if ( *(_BYTE *)(v626 + 3) )
      {
        v627 = *(_QWORD *)(v626 + 80);
      }
      else if ( *(_BYTE *)v626 == 2 )
      {
        v628 = *(__int64 **)(v626 + 48);
        v629 = *v628;
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*(_QWORD *)*v628 + 96LL))(v628, &v848);
        v14 = Table;
        sqlite3VtabImportErrmsg(v4, v629);
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        v627 = v848;
      }
      else
      {
        v630 = sqlite3VdbeCursorRestore(*(_QWORD *)(v624 + 8 * v623));
        v3 = 0;
        Table = v630;
        v14 = v630;
        if ( v630 )
          goto LABEL_1546;
        if ( *(_BYTE *)(v626 + 2) )
        {
          v10 = 1;
          *(_WORD *)(v625 + 20) = 1;
          goto LABEL_146;
        }
        v627 = sqlite3BtreeIntegerKey(*(_QWORD *)(v626 + 48));
        v3 = 0;
      }
LABEL_1195:
      *(_QWORD *)v625 = v627;
      goto LABEL_80;
    }
    if ( (unsigned int)v15 > 0xA3 )
    {
      if ( (unsigned int)v15 <= 0xAE )
      {
        if ( (_DWORD)v15 == 174 )
        {
          v765 = *((int *)v6 + 2);
          v837 = 0;
          v766 = v7 + 56 * v765;
          sqlite3VdbeMemSetNull(v766);
          v767 = (_QWORD *)*((_QWORD *)v6 + 2);
          v3 = 0;
          v768 = v767[10];
          if ( !v768 )
            goto LABEL_1406;
          v769 = *(__int64 **)(v768 + 16);
          v770 = *v769;
          sqlite3VtabLock();
          v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, unsigned int **))(v770 + 192))(
                  v769,
                  *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32)),
                  *v767,
                  *((unsigned int *)v6 + 3),
                  &v837);
          Table = v14;
          sqlite3VtabUnlock(v767[10]);
          v3 = 0;
          if ( v14 )
          {
            sqlite3_free(v837);
            goto LABEL_1522;
          }
          if ( !v837 )
          {
LABEL_1406:
            v4 = a1;
LABEL_1407:
            v7 = v835;
            goto LABEL_1408;
          }
          LOBYTE(v771) = 1;
          sqlite3VdbeMemSetStr(v766, v837, -1, v771, sqlite3_free);
          goto LABEL_854;
        }
        if ( (unsigned int)v15 <= 0xA9 )
        {
          if ( (_DWORD)v15 != 169 )
          {
            v747 = v15 - 164;
            if ( v747 )
            {
              v748 = v747 - 1;
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
            v751 = v7 + 56LL * *((int *)v6 + 1);
            if ( *((_DWORD *)v6 + 3) )
            {
              v14 = sqlite3VdbeMemAggValue(v751, v7 + 56LL * *((int *)v6 + 3), *((_QWORD *)v6 + 2));
              Table = v14;
              v751 = v7 + 56LL * *((int *)v6 + 3);
            }
            else
            {
              v14 = sqlite3VdbeMemFinalize(v751, *((_QWORD *)v6 + 2));
              Table = v14;
            }
            if ( !v14 )
            {
              sqlite3VdbeChangeEncoding(v751, v9);
              goto LABEL_244;
            }
            v813 = (const char *)sqlite3_value_text(v751);
            v814 = "%s";
            goto LABEL_1538;
          }
          if ( v6[12] || (*(_QWORD *)(v2 + 48) & 0x400000000LL) == 0 )
          {
            v752 = sqlite3BtreeLockTable(
                     *(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8),
                     *((unsigned int *)v6 + 2));
            v3 = 0;
            Table = v752;
            v14 = v752;
            if ( v752 )
            {
              if ( (_BYTE)v752 != 6 )
                goto LABEL_1546;
              sqlite3VdbeError(v4, "database table is locked: %s", *((_QWORD *)v6 + 2));
              goto LABEL_1523;
            }
            goto LABEL_52;
          }
          goto LABEL_1078;
        }
        v753 = v15 - 170;
        if ( v753 )
        {
          v754 = v753 - 1;
          if ( v754 )
          {
            v755 = v754 - 1;
            if ( v755 )
            {
              if ( v755 != 1 )
                goto LABEL_53;
              v756 = *((_QWORD *)v6 + 2);
              v837 = 0;
              v757 = *(__int64 **)(v756 + 16);
              if ( v757 )
              {
                v758 = *v757;
                if ( *v757 )
                {
                  Table = (*(__int64 (__fastcall **)(__int64 *, unsigned int **))(v758 + 48))(v757, &v837);
                  v14 = Table;
                  sqlite3VtabImportErrmsg(v4, v757);
                  v3 = 0;
                  if ( Table )
                    goto LABEL_1546;
                  LOBYTE(v759) = 2;
                  *(_QWORD *)v837 = v757;
                  v760 = allocateCursor(v4, *((unsigned int *)v6 + 1), 0, v759);
                  v3 = 0;
                  if ( v760 )
                  {
                    v10 = 1;
                    *(_QWORD *)(v760 + 48) = v837;
                    ++*((_DWORD *)v757 + 2);
                    goto LABEL_146;
                  }
                  (*(void (__fastcall **)(unsigned int *))(v758 + 56))(v837);
                  goto LABEL_1543;
                }
              }
              goto LABEL_1504;
            }
            *(_DWORD *)(v2 + 232) += v10;
            v75 = sqlite3VtabCallDestroy(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
            --*(_DWORD *)(v2 + 232);
            goto LABEL_153;
          }
          v856 = 0;
          v761 = *((int *)v6 + 2);
          *(_QWORD *)&v854 = 0;
          v853 = 0;
          v855 = 0;
          *((_QWORD *)&v854 + 1) = v2;
          Table = sqlite3VdbeMemCopy(&v853, v7 + 56 * v761);
          v14 = Table;
          v762 = sqlite3_value_text(&v853);
          if ( v762 )
          {
            v14 = sqlite3VtabCallCreate(v2, *((unsigned int *)v6 + 1), v762, v4 + 21);
            Table = v14;
          }
          sqlite3VdbeMemRelease(&v853);
        }
        else
        {
          v763 = *((_QWORD *)v6 + 2);
          v764 = sqlite3VtabBegin(v2, v763);
          v3 = 0;
          Table = v764;
          v14 = v764;
          if ( !v763 )
            goto LABEL_1246;
          sqlite3VtabImportErrmsg(v4, *(_QWORD *)(v763 + 16));
        }
        v3 = 0;
LABEL_1246:
        v76 = v14 == 0;
LABEL_154:
        if ( !v76 )
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
        v772 = v15 - 175;
        if ( !v772 )
        {
          v793 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v794 = (_QWORD *)sqlite3_malloc64(16);
          v795 = v794;
          if ( v794 )
          {
            *v794 = *(_QWORD *)(v793 + 48);
            v794[1] = v7 + 56LL * *((int *)v6 + 3);
            v796 = out2Prerelease(v4, v6);
            *(_WORD *)(v796 + 20) = 1;
            sqlite3VdbeMemSetPointer(v796, v795, "ValueList", sqlite3VdbeValueListFree);
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        v773 = v772 - 1;
        if ( !v773 )
        {
          v863 = 0;
          v865 = 0;
          memset(v861, 0, sizeof(v861));
          v866 = 0;
          v862 = 0;
          memset_0(&v864, 0, 0x45u);
          v785 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v786 = *((int *)v6 + 3);
          v787 = v7 + 56 * v786;
          if ( *(_BYTE *)(v785 + 2) )
          {
            sqlite3VdbeMemSetNull(v7 + 56 * v786);
            goto LABEL_422;
          }
          v788 = **(__int64 ***)(v785 + 48);
          v789 = *v788;
          BYTE8(v862) = v831;
          *((_QWORD *)&v861[0] + 1) = &v864;
          *(_QWORD *)&v861[0] = v787;
          v867 = 0x1000000;
          if ( (v6[2] & 1) != 0 )
          {
            sqlite3VdbeMemSetNull(v787);
            v790 = 1025;
            *(_DWORD *)v787 = 0;
          }
          else
          {
            v790 = *(_WORD *)(v787 + 20) & 0xF240 | 1;
          }
          *(_WORD *)(v787 + 20) = v790;
          v791 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v789 + 88))(
                   *(_QWORD *)(v785 + 48),
                   v861,
                   *((unsigned int *)v6 + 2));
          v4 = a1;
          Table = v791;
          v14 = v791;
          sqlite3VtabImportErrmsg(a1, v788);
          if ( SDWORD1(v862) > 0 )
          {
            v792 = (const char *)sqlite3_value_text(v787);
            sqlite3VdbeError(a1, "%s", v792);
            v14 = DWORD1(v862);
            Table = DWORD1(v862);
          }
          v9 = v831;
          sqlite3VdbeChangeEncoding(v787, v831);
          goto LABEL_50;
        }
        v774 = v773 - 1;
        if ( v774 )
        {
          v775 = v774 - 1;
          if ( v775 )
          {
            if ( v775 != 1 )
              goto LABEL_53;
            v776 = (_QWORD *)out2Prerelease(v4, v6);
            v777 = 32LL * *((int *)v6 + 1);
            v778 = *(_QWORD *)(v777 + *(_QWORD *)(v2 + 32) + 8);
            Page = 0;
            if ( *((_DWORD *)v6 + 3) )
            {
              Page = sqlite3BtreeLastPage(*(_QWORD *)(v777 + *(_QWORD *)(v2 + 32) + 8));
              if ( Page < *((_DWORD *)v6 + 3) )
                Page = *((_DWORD *)v6 + 3);
            }
            *v776 = (unsigned int)sqlite3BtreeMaxPageCount(v778, Page);
            goto LABEL_422;
          }
          v780 = (_QWORD *)out2Prerelease(v4, v6);
          *v780 = (unsigned int)sqlite3BtreeLastPage(*(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8));
LABEL_244:
          v3 = 0;
          goto LABEL_52;
        }
        v781 = *(_DWORD *)(v2 + 48);
        *(_QWORD *)(v2 + 48) |= 0x4000000uLL;
        v782 = *(_QWORD *)(*((_QWORD *)v6 + 2) + 16LL);
        v783 = v835 + 56LL * *((int *)v6 + 1);
        v784 = sqlite3VdbeChangeEncoding(v783, (unsigned int)v10);
        v3 = 0;
        v14 = v784;
        if ( v784 )
          goto LABEL_1546;
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v782 + 152LL))(v782, *(_QWORD *)(v783 + 8));
        v14 = Table;
        if ( (v781 & 0x4000000) == 0 )
          *(_QWORD *)(v2 + 48) &= ~0x4000000uLL;
        sqlite3VtabImportErrmsg(v4, v782);
        *((_DWORD *)v4 + 50) &= 0xFFFFFFFC;
        v3 = 0;
        if ( Table )
          goto LABEL_1546;
        goto LABEL_79;
      }
      v797 = v15 - 181;
      if ( v797 )
      {
        v798 = v797 - 1;
        if ( !v798 )
        {
          v810 = 56LL * *((int *)v6 + 1);
          v811 = 56LL * *((int *)v6 + 2);
          if ( ((unsigned __int8)v10 & *(_BYTE *)(v810 + v7 + 20)) != 0 )
          {
            *(_WORD *)(v811 + v7 + 20) &= ~0x800u;
          }
          else
          {
            *(_WORD *)(v811 + v7 + 20) |= 0x800u;
            *(_BYTE *)(v811 + v7 + 23) = *(_BYTE *)(v810 + v7);
          }
          goto LABEL_196;
        }
        v799 = v798 - 1;
        if ( !v799 )
        {
          v807 = 56LL * *((int *)v6 + 1);
          v808 = filterHash(v7, v6);
          v809 = (v808 % (8 * *(_DWORD *)(v807 + v7 + 16))) >> 3;
          *(_BYTE *)(v809 + *(_QWORD *)(v807 + v7 + 8)) |= 1 << ((v808 % (8 * *(_DWORD *)(v807 + v7 + 16))) & 7);
          goto LABEL_244;
        }
        if ( v799 != 1 )
          goto LABEL_53;
        goto LABEL_1442;
      }
      v812 = 56LL * *((int *)v6 + 1);
      v682 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v812 + v7 + 20) & 0x800) != 0 )
      {
        sqlite3VdbeMemSetInt64(v682, *(unsigned __int8 *)(v812 + v7 + 23));
        goto LABEL_244;
      }
LABEL_1260:
      sqlite3VdbeMemSetNull(v682);
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
            v683 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( *(_BYTE *)v683 == (_BYTE)v10 )
            {
              sqlite3VdbeSorterReset(v2, *(_QWORD *)(v683 + 48));
              goto LABEL_244;
            }
            v75 = sqlite3BtreeClearTableOfCursor(*(_QWORD *)(v683 + 48));
            goto LABEL_153;
          }
          v662 = v15 - 141;
          if ( v662 )
          {
            v663 = v662 - 1;
            if ( v663 )
            {
              v664 = v663 - 1;
              if ( !v664 )
              {
                v675 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
                if ( !*(_BYTE *)(v675 + 3) )
                  goto LABEL_53;
                v75 = sqlite3VdbeFinishMoveto(v675);
                goto LABEL_153;
              }
              v665 = v664 - 1;
              if ( !v665 )
              {
                LODWORD(v840) = 0;
                v671 = out2Prerelease(v4, v6);
                *(_WORD *)(v671 + 20) = 1;
                if ( *(_DWORD *)(v2 + 220) > *(_DWORD *)(v2 + 232) + 1 )
                {
                  v14 = 6;
                  *((_BYTE *)v4 + 196) = 2;
                  goto LABEL_1523;
                }
                v672 = *((_DWORD *)v6 + 3);
                v673 = *(_QWORD *)(v2 + 32);
                v674 = *((unsigned int *)v6 + 1);
                LODWORD(v840) = 0;
                v14 = sqlite3BtreeDropTable(*(_QWORD *)(32LL * (int)v672 + v673 + 8), v674, &v840);
                Table = v14;
                v3 = 0;
                *(_WORD *)(v671 + 20) = 4;
                *(_QWORD *)v671 = (int)v840;
                if ( v14 )
                  goto LABEL_1546;
                if ( (_DWORD)v840 )
                {
                  sqlite3RootPageMoved(v2, v672, (unsigned int)v840, *((unsigned int *)v6 + 1));
                  v10 = 1;
                  v842 = v672 + 1;
LABEL_59:
                  v9 = v831;
LABEL_60:
                  v5 = v834;
LABEL_61:
                  v13 = v832;
                  v3 = 0;
                  goto LABEL_53;
                }
                v13 = v832;
                v10 = 1;
                goto LABEL_623;
              }
              if ( v665 != 1 )
                goto LABEL_53;
              v666 = *(_QWORD *)(v2 + 32);
              v667 = *((unsigned int *)v6 + 1);
              v668 = 32LL * *((int *)v6 + 2);
              v848 = 0;
              v669 = sqlite3BtreeClearTable(*(_QWORD *)(v668 + v666 + 8), v667, &v848);
              v3 = 0;
              Table = v669;
              v14 = v669;
              if ( *((_DWORD *)v6 + 3) )
              {
                v670 = v848;
                v4[7] += v848;
                if ( *((int *)v6 + 3) > 0 )
                  *(_QWORD *)(56LL * *((int *)v6 + 3) + v7) += v670;
              }
              goto LABEL_1246;
            }
          }
          v676 = *((int *)v6 + 1);
          v677 = v4[15];
          v837 = 0;
          v678 = *(_QWORD *)(v677 + 8 * v676);
          v679 = sqlite3VdbeCursorRestore(v678);
          v3 = 0;
          Table = v679;
          v14 = v679;
          if ( v679 )
            goto LABEL_1546;
          if ( !*(_BYTE *)(v678 + 2) )
          {
            v837 = 0;
            v680 = sqlite3VdbeIdxRowid(v2, *(_QWORD *)(v678 + 48), &v837);
            v3 = 0;
            Table = v680;
            v14 = v680;
            if ( v680 )
              goto LABEL_1546;
            if ( *v6 == 0x8D )
            {
              v10 = v680 + 1;
              v681 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 3));
              *(_BYTE *)(v681 + 2) = 0;
              *(_QWORD *)(v681 + 80) = v837;
              *(_BYTE *)(v681 + 3) = v680 + 1;
              *(_DWORD *)(v681 + 32) = 0;
              *(_QWORD *)(v681 + 16) = *((_QWORD *)v6 + 2);
              *(_QWORD *)(v681 + 40) = v678;
              goto LABEL_195;
            }
            v287 = (unsigned int **)out2Prerelease(v4, v6);
            v288 = v837;
            goto LABEL_536;
          }
          v682 = v7 + 56LL * *((int *)v6 + 2);
          goto LABEL_1260;
        }
        v684 = v15 - 147;
        if ( !v684 )
        {
          LODWORD(v838) = 0;
          v700 = out2Prerelease(v4, v6);
          v701 = *(_QWORD *)(v2 + 32);
          v702 = (_QWORD *)v700;
          v703 = *((unsigned int *)v6 + 3);
          v704 = 32LL * *((int *)v6 + 1);
          LODWORD(v838) = 0;
          v705 = sqlite3BtreeCreateTable(*(_QWORD *)(v704 + v701 + 8), &v838, v703);
          v3 = 0;
          Table = v705;
          v14 = v705;
          if ( v705 )
            goto LABEL_1546;
          *v702 = (unsigned int)v838;
          goto LABEL_52;
        }
        v685 = v684 - 1;
        if ( !v685 )
        {
          *(_BYTE *)(v2 + 112) += v10;
          v695 = *(_QWORD *)(v2 + 512);
          v696 = *(_BYTE *)(v2 + 110);
          v697 = *(_DWORD *)(v2 + 744);
          v837 = 0;
          if ( ((unsigned __int8)v10 & v6[4]) != 0 )
          {
            *(_QWORD *)(v2 + 512) = 0;
            *(_BYTE *)(v2 + 110) = 0;
          }
          if ( (v6[4] & 2) != 0 )
            *(_DWORD *)(v2 + 744) = *((_DWORD *)v6 + 2);
          v698 = sqlite3_exec(v2, *((_QWORD *)v6 + 2), 0, 0, (__int64)&v837);
          v699 = (const char *)v837;
          v3 = 0;
          --*(_BYTE *)(v2 + 112);
          v14 = v698;
          Table = v698;
          *(_QWORD *)(v2 + 512) = v695;
          *(_BYTE *)(v2 + 110) = v696;
          *(_DWORD *)(v2 + 744) = v697;
          if ( !v699 && !v698 )
            goto LABEL_79;
          sqlite3VdbeError(v4, "%s", v699);
          sqlite3_free(v837);
LABEL_1288:
          if ( v14 != 7 )
            goto LABEL_1523;
          goto LABEL_1543;
        }
        v686 = v685 - 1;
        if ( v686 )
        {
          v687 = v686 - 1;
          if ( v687 )
          {
            if ( v687 != 1 )
              goto LABEL_53;
            sqlite3UnlinkAndDeleteTable(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
            goto LABEL_244;
          }
          v75 = sqlite3AnalysisLoad(v2, *((unsigned int *)v6 + 1));
          goto LABEL_153;
        }
        v688 = *((int *)v6 + 1);
        v689 = *(_QWORD *)(v2 + 32);
        v844 = 0;
        *(_QWORD *)&v846 = 0;
        v845 = 0;
        if ( *((_QWORD *)v6 + 2) )
        {
          LODWORD(v845) = v688;
          *(_QWORD *)&v844 = v2;
          *((_QWORD *)&v844 + 1) = v4 + 21;
          DWORD2(v845) = 0;
          v691 = 32 * v688;
          v692 = sqlite3BtreeLastPage(*(_QWORD *)(v689 + v691 + 8));
          v693 = *(_QWORD *)(v2 + 32);
          LODWORD(v846) = v692;
          v694 = sqlite3MPrintf(
                   v2,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(v693 + v691),
                   "sqlite_master",
                   *((_QWORD *)v6 + 2));
          if ( !v694 )
          {
            v14 = 7;
LABEL_1533:
            sqlite3ResetAllSchemasOfConnection(v2);
            goto LABEL_1288;
          }
          *(_BYTE *)(v2 + 197) = 1;
          DWORD1(v845) = 0;
          HIDWORD(v845) = 0;
          v14 = sqlite3_exec(v2, v694, (unsigned int)sqlite3InitCallback, (unsigned int)&v844, 0);
          Table = v14;
          if ( !v14 )
          {
            v14 = DWORD1(v845);
            Table = DWORD1(v845);
            if ( !DWORD1(v845) && !HIDWORD(v845) )
            {
              v14 = sqlite3CorruptError(100154);
              Table = v14;
            }
          }
          sqlite3DbFreeNN(v2, v694);
          v3 = 0;
          *(_BYTE *)(v2 + 197) = 0;
          v10 = 1;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v688 + v689 + 24));
          *(_DWORD *)(v2 + 44) &= ~0x10u;
          inited = sqlite3InitOne(v2, (unsigned int)v688, v4 + 21, *((unsigned __int16 *)v6 + 1));
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
          v725 = *((int *)v6 + 2);
          if ( (*(_DWORD *)(v2 + 48) & 0x80000) != 0 )
          {
            *(_QWORD *)(v2 + 768) += v725;
          }
          else if ( *((_DWORD *)v6 + 1) )
          {
            *(_QWORD *)(v2 + 760) += v725;
          }
          else
          {
            v4[10] += v725;
          }
          goto LABEL_53;
        }
        v706 = v15 - 153;
        if ( !v706 )
        {
          v286 = out2Prerelease(v4, v6);
          *(_WORD *)(v286 + 20) = 8;
          goto LABEL_534;
        }
        v707 = v706 - 1;
        if ( !v707 )
        {
          sqlite3UnlinkAndDeleteTrigger(v2, *((unsigned int *)v6 + 1), *((_QWORD *)v6 + 2));
          goto LABEL_244;
        }
        v708 = v707 - 1;
        if ( !v708 )
        {
          v713 = *((int *)v6 + 1);
          v714 = *((_QWORD *)v6 + 2);
          v715 = 56 * v713;
          v716 = v713 + 1;
          LODWORD(v838) = 0;
          v717 = *(_QWORD *)(v2 + 32);
          v718 = 56 * *((_DWORD *)v6 + 3);
          v837 = 0;
          v719 = v7 + 56LL * v716;
          Table = sqlite3BtreeIntegrityCheck(
                    v2,
                    *(_QWORD *)(32LL * *((unsigned __int16 *)v6 + 1) + v717 + 8),
                    (int)v714 + 4,
                    (int)v7 + v718,
                    *((_DWORD *)v6 + 2),
                    (int)v10 + *(_DWORD *)(v715 + v7),
                    (__int64)&v838,
                    (__int64)&v837);
          v14 = Table;
          sqlite3VdbeMemSetNull(v719);
          if ( (_DWORD)v838 )
          {
            if ( Table )
            {
              sqlite3_free(v837);
              goto LABEL_1523;
            }
            LOBYTE(v720) = 1;
            *(_QWORD *)(v715 + v7) -= (int)v838 - 1;
            sqlite3VdbeMemSetStr(v719, v837, -1, v720, sqlite3_free);
          }
          v9 = v831;
          sqlite3VdbeChangeEncoding(v719, v831);
          goto LABEL_1308;
        }
        v709 = v708 - 1;
        if ( !v709 )
        {
          v710 = *((int *)v6 + 1);
          v711 = *((int *)v6 + 2);
          v712 = v7 + 56 * v710;
          if ( (*(_BYTE *)(v712 + 20) & 0x10) != 0 || !(unsigned int)sqlite3VdbeMemSetRowSet(v7 + 56 * v710) )
          {
            sqlite3RowSetInsert(*(_QWORD *)(v712 + 8), *(_QWORD *)(56 * v711 + v7));
            goto LABEL_422;
          }
          goto LABEL_1543;
        }
        if ( v709 != 1 )
          goto LABEL_53;
        v326 = out2Prerelease(v4, v6);
        v325 = *(_QWORD *)(v4[33] + 24)
             + 56LL * (*((_DWORD *)v6 + 1) + *(_DWORD *)(*(_QWORD *)(v4[33] + 16) + 24LL * *(int *)(v4[33] + 76) + 4));
        goto LABEL_598;
      }
      v726 = v15 - 159;
      if ( !v726 )
      {
        v739 = v4[33];
        if ( v739 )
        {
          while ( *(_QWORD *)(v739 + 8) )
            v739 = *(_QWORD *)(v739 + 8);
          v740 = (_QWORD *)(*(_QWORD *)(v739 + 24) + 56LL * *((int *)v6 + 1));
        }
        else
        {
          v740 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 1));
        }
        sqlite3VdbeMemIntegerify(v740);
        v741 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 2));
        sqlite3VdbeMemIntegerify(v741);
        v3 = 0;
        v13 = v832;
        v10 = 1;
        if ( *v740 < *v741 )
          *v740 = *v741;
        goto LABEL_623;
      }
      v727 = v726 - 1;
      if ( !v727 )
      {
        v734 = *((int *)v6 + 3);
        v735 = 56LL * *((int *)v6 + 1);
        v837 = 0;
        v625 = out2Prerelease(v4, v6);
        v3 = 0;
        v837 = *(unsigned int **)(v735 + v835);
        if ( (__int64)v837 <= 0 )
        {
          v7 = v835;
        }
        else
        {
          v736 = 56 * v734;
          v7 = v835;
          v737 = *(_QWORD *)(v736 + v835);
          if ( v737 <= 0 )
            v737 = 0;
          v738 = sqlite3AddInt64(&v837, v737);
          v3 = 0;
          if ( !v738 )
          {
            v627 = (__int64)v837;
            goto LABEL_1195;
          }
        }
        *(_QWORD *)v625 = -1;
        goto LABEL_80;
      }
      if ( (unsigned int)(v727 - 1) > 1 )
        goto LABEL_53;
      v728 = *((unsigned __int16 *)v6 + 1);
      v729 = sqlite3DbMallocRawNN(v2, 8 * v728 + 104);
      if ( !v729 )
        goto LABEL_1543;
      *(_QWORD *)(v729 + 16) = 0;
      v730 = v729 + 8 * (v728 + 6);
      *(_QWORD *)v729 = v730;
      sqlite3VdbeMemInit(v730, v2, 1);
      v7 = v835;
      *(_QWORD *)(v729 + 8) = *((_QWORD *)v6 + 2);
      *(_BYTE *)(v729 + 42) = v728;
      *(_DWORD *)(v729 + 32) = -1431655765 * ((__int64)&v6[-v834] >> 3);
      v9 = v831;
      *(_QWORD *)(v729 + 24) = v4;
      *(_BYTE *)(v729 + 41) = 0;
      *(_DWORD *)(v729 + 36) = 0;
      LODWORD(v10) = 1;
      *(_BYTE *)(v729 + 40) = v831;
      *(_WORD *)v6 = -3677;
      *((_QWORD *)v6 + 2) = v729;
    }
    v731 = (_DWORD *)*((_QWORD *)v6 + 2);
    v732 = v7 + 56LL * *((int *)v6 + 3);
    if ( *((_QWORD *)v731 + 2) != v732 )
    {
      v733 = *((unsigned __int8 *)v731 + 42);
      *((_QWORD *)v731 + 2) = v732;
      while ( 1 )
      {
        v733 -= v10;
        if ( v733 < 0 )
          break;
        *(_QWORD *)&v731[2 * v733 + 12] = v7 + 56LL * (v733 + *((_DWORD *)v6 + 2));
      }
    }
    *(_DWORD *)(v732 + 16) += v10;
    v742 = v731 + 12;
    v743 = *((_QWORD *)v731 + 1);
    v744 = *((unsigned __int8 *)v731 + 42);
    if ( *((_DWORD *)v6 + 1) )
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v743 + 48))(v731, v744, v742);
    else
      (*(void (__fastcall **)(_DWORD *, __int64, _DWORD *))(v743 + 24))(v731, v744, v742);
    v745 = v731[9];
    v3 = 0;
    if ( !v745 )
      goto LABEL_1408;
    if ( v745 > 0 )
    {
      v746 = (const char *)sqlite3_value_text(*(_QWORD *)v731);
      sqlite3VdbeError(v4, "%s", v746);
      v14 = v731[9];
      Table = v14;
    }
    if ( *((_BYTE *)v731 + 41) )
    {
      if ( *((_DWORD *)v6 - 5) )
        sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 - 5), 1);
      *((_BYTE *)v731 + 41) = 0;
    }
    sqlite3VdbeMemRelease(*(_QWORD *)v731);
    v3 = 0;
    v10 = 1;
    *(_WORD *)(*(_QWORD *)v731 + 20LL) = 1;
    v731[9] = 0;
    if ( v14 )
      goto LABEL_1546;
    goto LABEL_195;
  }
  if ( (_DWORD)v15 == 92 )
  {
    if ( ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 1) + v7 + 20)) != 0
      || ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 3) + v7 + 20)) != 0 )
    {
      v344 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v344 + 20) & 0x9000) == 0 )
      {
        *(_WORD *)(v344 + 20) = v10;
        goto LABEL_53;
      }
      v141 = v7 + 56LL * *((int *)v6 + 2);
      goto LABEL_248;
    }
    v322 = *((int *)v6 + 2);
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
            v103 = 56LL * *((int *)v6 + 1);
            *(_QWORD *)(v103 + v7) = *((_DWORD *)v6 + 3) - (int)v10;
            *(_WORD *)(v103 + v7 + 20) = 4;
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
                          && (!(unsigned int)sqlite3Strlen30(v26, v27, v28)
                           || !(unsigned int)sqlite3PagerWalSupported(v23)) )
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
                                v29 = sqlite3PagerSetJournalMode(v23, v21);
                                *(_WORD *)(v20 + 20) = 8706;
                                v30 = sqlite3JournalModename(v29);
                                *(_QWORD *)(v20 + 8) = v30;
                                v9 = v831;
                                *(_DWORD *)(v20 + 16) = sqlite3Strlen30(v30, v31, v32);
                                *(_BYTE *)(v20 + 22) = 1;
                                sqlite3VdbeChangeEncoding(v20, v831);
                                v4 = a1;
LABEL_50:
                                v3 = 0;
                                if ( v14 )
                                  goto LABEL_1546;
LABEL_51:
                                v7 = v835;
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
                        v813 = "into";
                        v14 = 1;
                        v814 = "cannot change %s wal mode from within a transaction";
                        if ( v21 != 5 )
                          v813 = "out of";
LABEL_1538:
                        sqlite3VdbeError(v4, v814, v813);
                        goto LABEL_1523;
                      }
                      v33 = *((_DWORD *)v6 + 2);
                      v34 = *((_DWORD *)v6 + 1);
                      v868 = 0;
                      v869 = -1;
                      v35 = sqlite3Checkpoint(v2, v34, v33, (unsigned int)&v869, (__int64)&v869 + 4);
                      v3 = 0;
                      Table = v35;
                      v14 = v35;
                      if ( v35 )
                      {
                        if ( v35 != 5 )
                          goto LABEL_1546;
                        v14 = 0;
                        Table = 0;
                        v868 = 1;
                      }
                      v36 = 0;
                      v37 = v7 + 56LL * *((int *)v6 + 3);
                      do
                      {
                        sqlite3VdbeMemSetInt64(v37, *(&v868 + v36));
                        v10 = 1;
                        v37 += 56;
                        ++v36;
                      }
                      while ( v36 != 3 );
                      goto LABEL_59;
                    }
                    v38 = *((unsigned int *)v6 + 2);
                    LODWORD(v838) = 0;
                    if ( (_DWORD)v38 && (*(_QWORD *)(v2 + 48) & 0x200100000LL) != 0 )
                    {
                      v14 = (*(_QWORD *)(v2 + 48) & 0x100000LL) != 0 ? 8 : 11;
                      goto LABEL_1546;
                    }
                    v39 = *(_QWORD *)(v2 + 32);
                    v40 = 32LL * *((int *)v6 + 1);
                    v41 = *(_QWORD *)(v40 + v39 + 8);
                    if ( v41 )
                    {
                      v42 = sqlite3BtreeBeginTrans(*(_QWORD *)(v40 + v39 + 8), v38, &v838);
                      v3 = 0;
                      Table = v42;
                      v14 = v42;
                      if ( v42 )
                      {
                        if ( (_BYTE)v42 == 5 )
                        {
                          *((_DWORD *)v4 + 13) = v42;
                          *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v834] >> 3);
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
                          && ((_DWORD)v838 != *((_DWORD *)v6 + 3)
                           || *(_DWORD *)(*(_QWORD *)(v40 + v39 + 24) + 4LL) != *((_DWORD *)v6 + 4)) )
                        {
                          v815 = v4[21];
                          if ( v815 )
                            sqlite3DbFreeNN(v2, v815);
                          v4[21] = sqlite3DbStrDup(v2, "database schema has changed");
                          if ( **(_DWORD **)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 24) != (_DWORD)v838 )
                            sqlite3ResetOneSchema(v2);
                          v14 = 17;
                          *((_DWORD *)v4 + 50) = v4[25] & 0xFFFFFFEC | 1;
                          goto LABEL_1523;
                        }
                        goto LABEL_79;
                      }
                      v43 = *((_DWORD *)v4 + 16);
                      if ( !v43 )
                      {
                        v43 = ++*(_DWORD *)(v2 + 756) + *(_DWORD *)(v2 + 752);
                        *((_DWORD *)v4 + 16) = v43;
                      }
                      v44 = sqlite3VtabSavepoint(v2, 0, (unsigned int)(v43 - 1));
                      v3 = 0;
                      Table = v44;
                      v14 = v44;
                      if ( !v44 )
                      {
                        v14 = sqlite3BtreeBeginStmt(v41, *((unsigned int *)v4 + 16));
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
                  v816 = *((_DWORD *)v6 + 1);
                  v817 = *((_DWORD *)v6 + 2);
                  if ( v816 != *(unsigned __int8 *)(v2 + 101) )
                  {
                    if ( v817 )
                    {
                      sqlite3RollbackAll(v2, 516);
                      v818 = 1;
                    }
                    else
                    {
                      if ( v816 && *(int *)(v2 + 224) > 0 )
                      {
                        sqlite3VdbeError(v4, "cannot commit transaction - SQL statements in progress");
                        goto LABEL_1485;
                      }
                      v14 = sqlite3VdbeCheckFk(v4, (unsigned int)v10);
                      if ( v14 )
                        goto LABEL_1564;
                      v818 = v816;
                    }
                    *(_BYTE *)(v2 + 101) = v818;
                    if ( (unsigned int)sqlite3VdbeHalt(v4) == 5 )
                    {
                      v14 = 5;
                      *((_DWORD *)v4 + 12) = -1431655765 * ((__int64)&v6[-v834] >> 3);
                      *(_BYTE *)(v2 + 101) = 1 - v816;
                      *((_DWORD *)v4 + 13) = 5;
                    }
                    else
                    {
                      sqlite3CloseSavepoints(v2);
                      v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
                    }
                    goto LABEL_1564;
                  }
                  if ( v816 )
                  {
                    v819 = "cannot rollback - no transaction is active";
                    if ( !v817 )
                      v819 = "cannot commit - no transaction is active";
                    sqlite3VdbeError(v4, v819);
                  }
                  else
                  {
                    sqlite3VdbeError(v4, "cannot start a transaction within a transaction");
                  }
                }
                else
                {
                  v45 = *((_DWORD *)v6 + 1);
                  v46 = (_BYTE *)*((_QWORD *)v6 + 2);
                  v843 = v45;
                  if ( !v45 )
                  {
                    if ( *(int *)(v2 + 224) <= 0 )
                    {
                      if ( v46 )
                      {
                        v48 = -1;
                        do
                          ++v48;
                        while ( v46[v48] );
                        v47 = v48 & 0x3FFFFFFF;
                      }
                      else
                      {
                        v47 = 0;
                      }
                      v49 = sqlite3VtabSavepoint(v2, 0, (unsigned int)(*(_DWORD *)(v2 + 752) + *(_DWORD *)(v2 + 756)));
                      v3 = 0;
                      Table = v49;
                      v14 = v49;
                      if ( !v49 )
                      {
                        v50 = (_QWORD *)sqlite3DbMallocRawNN(v2, v47 + 33LL);
                        v3 = 0;
                        v51 = v50;
                        if ( v50 )
                        {
                          *v50 = v50 + 4;
                          memcpy_0(v50 + 4, v46, v47 + 1);
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
                          v51[3] = *(_QWORD *)(v2 + 736);
                          v52 = *(_QWORD *)(v2 + 760);
                          *(_QWORD *)(v2 + 736) = v51;
                          v51[1] = v52;
                          v51[2] = *(_QWORD *)(v2 + 768);
                        }
                        goto LABEL_143;
                      }
                      goto LABEL_1546;
                    }
                    sqlite3VdbeError(v4, "cannot open savepoint - SQL statements in progress");
                    goto LABEL_1485;
                  }
                  v53 = *(_QWORD **)(v2 + 736);
                  for ( m = 0; ; ++m )
                  {
                    LODWORD(v840) = m;
                    if ( !v53 )
                      break;
                    v55 = sqlite3StrICmp(*v53, v46);
                    v3 = 0;
                    if ( !v55 )
                    {
                      v10 = 1;
                      if ( *(int *)(v2 + 224) <= 0 || v45 != 1 )
                      {
                        v56 = (unsigned int *)(v53 + 3);
                        v837 = (unsigned int *)(v53 + 3);
                        if ( v53[3] || !*(_BYTE *)(v2 + 109) )
                        {
                          LODWORD(v838) = 0;
                        }
                        else
                        {
                          LODWORD(v838) = 1;
                          v57 = 1;
                          if ( v45 == 1 )
                          {
                            v58 = sqlite3VdbeCheckFk(a1, 1);
                            if ( !v58 )
                            {
                              *(_BYTE *)(v839 + 101) = 1;
                              v59 = sqlite3VdbeHalt(a1);
                              v60 = v839;
                              if ( v59 == 5 )
                              {
                                v4 = a1;
                                v14 = 5;
                                *((_DWORD *)a1 + 12) = -1431655765 * ((__int64)&v6[-v834] >> 3);
                                *(_BYTE *)(v60 + 101) = 0;
                                *((_DWORD *)a1 + 13) = 5;
                                goto LABEL_1565;
                              }
                              v61 = *((_DWORD *)a1 + 13);
                              v3 = 0;
                              Table = v61;
                              if ( v61 )
                                *(_BYTE *)(v839 + 101) = 0;
                              else
                                *(_BYTE *)(v839 + 109) = 0;
                              v62 = (int *)(v60 + 752);
                              v10 = 1;
                              goto LABEL_129;
                            }
                            v14 = v58;
                            v4 = a1;
LABEL_1564:
                            v60 = v839;
                            goto LABEL_1565;
                          }
                        }
                        v62 = (int *)(v2 + 752);
                        v63 = *v62;
                        if ( v45 == 2 )
                        {
                          v64 = v839;
                          v65 = 0;
                          v66 = *(_DWORD *)(v839 + 44) & 1;
                          if ( *(int *)(v839 + 40) > 0 )
                          {
                            do
                            {
                              v67 = sqlite3BtreeTripAllCursors(
                                      *(_QWORD *)(32LL * v65 + *(_QWORD *)(v64 + 32) + 8),
                                      516,
                                      v66 ^ 1u);
                              v3 = 0;
                              Table = v67;
                              if ( v67 )
                                goto LABEL_1544;
                              v64 = v839;
                              v10 = 1;
                              ++v65;
                            }
                            while ( v65 < *(_DWORD *)(v839 + 40) );
                            m = (unsigned int)v840;
                          }
                        }
                        else
                        {
                          v66 = 0;
                        }
                        v60 = v839;
                        m = v63 + ~m;
                        v68 = 0;
                        if ( *(int *)(v839 + 40) > 0 )
                        {
                          v69 = v843;
                          while ( 1 )
                          {
                            v61 = sqlite3BtreeSavepoint(*(_QWORD *)(32LL * v68 + *(_QWORD *)(v60 + 32) + 8), v69, m);
                            v3 = 0;
                            Table = v61;
                            if ( v61 )
                              goto LABEL_1544;
                            v60 = v839;
                            v10 = 1;
                            if ( ++v68 >= *(_DWORD *)(v839 + 40) )
                              goto LABEL_123;
                          }
                        }
                        v61 = Table;
LABEL_123:
                        if ( v66 )
                        {
                          for ( n = *(_QWORD *)(v60 + 8); n; n = *(_QWORD *)(n + 16) )
                          {
                            *(_DWORD *)(n + 200) &= ~2u;
                            *(_DWORD *)(n + 200) |= 1u;
                          }
                          sqlite3ResetAllSchemasOfConnection(v60);
                          v60 = v839;
                          v10 = 1;
                          v61 = Table;
                          *(_DWORD *)(v839 + 44) |= 1u;
                          v3 = 0;
                        }
                        v56 = v837;
                        v57 = v838;
                        v45 = v843;
LABEL_129:
                        if ( v61 )
                        {
LABEL_1544:
                          v14 = Table;
                        }
                        else
                        {
                          v71 = *(_QWORD **)(v60 + 736);
                          if ( v71 != v53 )
                          {
                            do
                            {
                              *(_QWORD *)(v60 + 736) = v71[3];
                              sqlite3DbFreeNN(v60, v71);
                              v60 = v839;
                              v10 = 1;
                              --*v62;
                              v71 = *(_QWORD **)(v60 + 736);
                            }
                            while ( v71 != v53 );
                            v3 = 0;
                          }
                          if ( v45 == 1 )
                          {
                            *(_QWORD *)(v60 + 736) = *(_QWORD *)v56;
                            sqlite3DbFreeNN(v60, v53);
                            v3 = 0;
                            if ( !v57 )
                            {
                              --*v62;
                              v72 = v839;
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
                            v7 = v835;
LABEL_146:
                            v5 = v834;
LABEL_147:
                            v13 = v832;
LABEL_148:
                            v9 = v831;
LABEL_53:
                            v2 = v839;
                            v6 += 24;
                            v8 = v852;
                            goto LABEL_9;
                          }
                          v72 = v839;
                          *(_QWORD *)(v839 + 760) = v53[1];
                          *(_QWORD *)(v72 + 768) = v53[2];
                          if ( v57 && v45 != 2 )
                          {
                            v14 = Table;
                            v4 = a1;
                            goto LABEL_144;
                          }
LABEL_138:
                          v73 = sqlite3VtabSavepoint(v72, v45, m);
                          v3 = 0;
                          Table = v73;
                          v14 = v73;
                          if ( !v73 )
                            goto LABEL_142;
                        }
LABEL_1545:
                        v4 = a1;
LABEL_1546:
                        v823 = v839;
                        if ( *(_BYTE *)(v839 + 103) == (_BYTE)v3 )
                        {
                          if ( v14 == 8458 )
                          {
                            v14 = sqlite3CorruptError(102186);
                            v3 = 0;
                          }
                        }
                        else
                        {
                          v14 = 7;
                        }
                        if ( v4[21] == v3 && v14 != 3082 )
                        {
                          v824 = (const char *)sqlite3ErrStr(v14);
                          sqlite3VdbeError(v4, "%s", v824);
                        }
                        *((_DWORD *)v4 + 13) = v14;
                        sqlite3SystemError(v823, v14);
                        sqlite3_log(
                          v14,
                          "statement aborts at %d: [%s] %s",
                          -1431655765 * ((__int64)&v6[-v834] >> 3),
                          (const char *)v4[31],
                          (const char *)v4[21]);
                        if ( *((_BYTE *)v4 + 199) == 2 )
                          sqlite3VdbeHalt(v4);
                        if ( v14 == 3082 )
                        {
                          sqlite3OomFault(v823);
                          goto LABEL_1557;
                        }
                        if ( v14 == 11 )
                        {
                          v60 = v823;
                          if ( !*(_BYTE *)(v823 + 101) )
                            *(_QWORD *)(v823 + 48) |= 0x200000000uLL;
                        }
                        else
                        {
LABEL_1557:
                          v60 = v823;
                        }
                        v14 = 1;
                        if ( v842 )
                        {
                          sqlite3ResetOneSchema(v60);
                          v60 = v823;
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
                    v53 = (_QWORD *)v53[3];
                  }
                  v4 = a1;
                  sqlite3VdbeError(a1, "no such savepoint: %s", v46);
                }
                v14 = 1;
                goto LABEL_1523;
              }
              if ( *((_DWORD *)v6 + 2) )
                v74 = v7 + 56LL * *((int *)v6 + 2);
              else
                v74 = 0;
              v75 = sqlite3RunVacuum(v4 + 21, v2, *((unsigned int *)v6 + 1), v74);
              goto LABEL_153;
            }
            v77 = v15 - 6;
            if ( v77 )
            {
              v78 = v77 - 1;
              if ( v78 )
              {
                v79 = v78 - 1;
                if ( v79 )
                {
                  v80 = v79 - 1;
                  if ( v80 )
                  {
                    if ( v80 != 1 )
                      goto LABEL_53;
                    v81 = 56LL * *((int *)v6 + 1);
                    *(_WORD *)(v81 + v7 + 20) = 4;
                    *(_QWORD *)(v81 + v7) = (int)(-1431655765 * ((__int64)&v6[-v5] >> 3));
                  }
                  goto LABEL_504;
                }
LABEL_1442:
                v800 = *(_BYTE *)(v2 + 110);
                if ( (v800 & 0x41) != 0 && *((_BYTE *)v4 + 197) != 0xFE )
                {
                  v801 = (const char *)*((_QWORD *)v6 + 2);
                  if ( v801 || (v801 = (const char *)v4[31]) != 0 )
                  {
                    if ( (v800 & 0x40) != 0 )
                    {
                      v802 = sqlite3VdbeExpandSql(v4, v801);
                      (*(void (__fastcall **)(_QWORD, __int64))(v2 + 248))(*(_QWORD *)(v2 + 256), v802);
                      sqlite3_free(v802);
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
                      v803 = sqlite3MPrintf(v2, "-- %s", v801);
                      (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v2 + 248))(
                        1,
                        *(_QWORD *)(v2 + 256),
                        v4,
                        v803);
                      sqlite3DbFree(v2, v803);
                    }
                    v5 = v834;
                    v3 = 0;
                    v13 = v832;
                    v10 = 1;
                  }
                }
                v804 = *((_DWORD *)v6 + 1);
                if ( v804 >= dword_180329B28 )
                {
                  if ( *v6 == 0xB8 )
                    goto LABEL_53;
                  for ( ii = v10; ii < *((_DWORD *)v4 + 36); ii += v10 )
                  {
                    v806 = v4[17];
                    if ( *(_BYTE *)(v806 + 24LL * ii) == 15 )
                      *(_DWORD *)(v806 + 24LL * ii + 4) = 0;
                  }
                  v804 = 0;
                }
                *((_DWORD *)v6 + 1) = v804 + 1;
                *((_DWORD *)v4 + 59) += v10;
                goto LABEL_215;
              }
              v837 = 0;
              if ( !*(_BYTE *)(v2 + 103) )
              {
                v82 = *(__int64 **)(*((_QWORD *)v6 + 2) + 16LL);
                if ( v82 )
                {
                  v3 = *v82;
                  if ( *v82 )
                  {
                    if ( !*(_QWORD *)(v3 + 104) )
                    {
                      v3 = 0;
                      goto LABEL_952;
                    }
                    v83 = 0;
                    v84 = *((unsigned int *)v6 + 2);
                    v85 = *(_BYTE *)(v2 + 108);
                    v86 = v4[14];
                    v87 = v7 + 56LL * *((int *)v6 + 3);
                    if ( (int)v84 > 0 )
                    {
                      do
                      {
                        v88 = (unsigned int)v83++;
                        *(_QWORD *)(v86 + 8 * v88) = v87;
                        v87 += 56;
                      }
                      while ( v83 < (int)v84 );
                      v7 = v835;
                    }
                    *(_BYTE *)(v2 + 108) = v6[2];
                    Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int **))(v3 + 104))(
                              v82,
                              v84,
                              v86,
                              &v837);
                    *(_BYTE *)(v2 + 108) = v85;
                    v14 = Table;
                    sqlite3VtabImportErrmsg(v4, v82);
                    v3 = 0;
                    if ( !Table )
                    {
                      if ( *((_DWORD *)v6 + 1) )
                        *(_QWORD *)(v2 + 56) = v837;
                      goto LABEL_172;
                    }
                    if ( (_BYTE)Table != 19 || !*(_BYTE *)(*((_QWORD *)v6 + 2) + 28LL) )
                    {
LABEL_172:
                      v10 = 1;
                      ++v4[7];
                      goto LABEL_173;
                    }
                    v89 = *((_WORD *)v6 + 1);
                    if ( v89 != 4 )
                    {
                      if ( v89 == 5 )
                        LOBYTE(v89) = 2;
                      *((_BYTE *)v4 + 196) = v89;
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
            v90 = 56LL * *((int *)v6 + 3);
            v91 = a1[14];
            v92 = (int *)(v90 + v7 + 56);
            v93 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v94 = *v92;
            v95 = *(__int64 ***)(v93 + 48);
            v96 = *(unsigned int *)(v90 + v835);
            v97 = *v95;
            v98 = **v95;
            if ( *v92 > 0 )
            {
              do
              {
                v99 = (unsigned int)v3;
                LODWORD(v3) = v3 + 1;
                *(_QWORD *)(v91 + 8 * v99) = &v92[14 * (int)v3];
              }
              while ( (int)v3 < v94 );
            }
            HIDWORD(v830) = HIDWORD(v91);
            v100 = (*(__int64 (__fastcall **)(__int64 **, __int64, _QWORD))(v98 + 64))(v95, v96, *((_QWORD *)v6 + 2));
            v101 = v97;
            Table = v100;
            v4 = a1;
            v14 = v100;
            sqlite3VtabImportErrmsg(a1, v101);
            v3 = 0;
            if ( v14 )
              goto LABEL_1546;
            v102 = (*(__int64 (__fastcall **)(__int64 **))(v98 + 80))(v95);
            v3 = 0;
            v10 = 1;
            *(_BYTE *)(v93 + 2) = 0;
            if ( !v102 )
              goto LABEL_145;
          }
          goto LABEL_1219;
        }
        if ( (unsigned int)v15 <= 0x11 )
        {
          if ( (_DWORD)v15 == 17 )
          {
            v123 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((_DWORD *)v6 + 3) == 0);
            v3 = 0;
            v10 = 1;
            if ( v123 )
              goto LABEL_195;
            goto LABEL_1219;
          }
          v104 = v15 - 12;
          if ( v104 )
          {
            v105 = v104 - 1;
            if ( v105 )
            {
              v106 = v105 - 1;
              if ( v106 )
              {
                v107 = v106 - 1;
                if ( v107 )
                {
                  if ( v107 != 1 )
                    goto LABEL_53;
                  v108 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((unsigned int *)v6 + 3));
                  v3 = 0;
                  v109 = v108 == 0;
                  goto LABEL_194;
                }
                v110 = v4[33];
                if ( v110 )
                {
                  v111 = *(_QWORD *)(v110 + 40);
                  v112 = (unsigned __int64)(-1431655765 * (unsigned int)((__int64)&v6[-v4[17]] >> 3)) >> 3;
                  v113 = (-85 * (unsigned __int8)((__int64)&v6[-v4[17]] >> 3)) & 7;
                  v114 = *(unsigned __int8 *)(v112 + v111);
                  if ( !_bittest(&v114, v113) )
                  {
                    v115 = v114 | (1 << v113);
                    v13 = v832;
                    *(_BYTE *)(v112 + v111) = v115;
LABEL_201:
                    *((_DWORD *)v6 + 1) = *(_DWORD *)(v4[17] + 4);
LABEL_202:
                    v5 = v834;
                    goto LABEL_53;
                  }
                }
                else if ( *(_DWORD *)(v4[17] + 4) != *((_DWORD *)v6 + 1) )
                {
                  goto LABEL_201;
                }
LABEL_214:
                v5 = v834;
LABEL_215:
                v4 = a1;
                v7 = v835;
                v6 = (unsigned __int8 *)(v5 + 24LL * (*((_DWORD *)v6 + 2) - (int)v10));
                goto LABEL_196;
              }
              if ( (int)v13 >= 0 )
              {
                if ( (_DWORD)v13 )
                  v116 = *((_DWORD *)v6 + 3);
                else
                  v116 = *((_DWORD *)v6 + 2);
              }
              else
              {
                v116 = *((_DWORD *)v6 + 1);
              }
              v117 = v116 - (int)v10;
LABEL_206:
              v6 = (unsigned __int8 *)(v5 + 24 * v117);
              goto LABEL_53;
            }
            v118 = v7 + 56LL * *((int *)v6 + 1);
            v119 = *(_WORD *)(v118 + 20);
            if ( (v119 & 4) == 0 )
            {
              LOBYTE(v5) = v9;
              LOBYTE(v13) = 67;
              applyAffinity(v7 + 56LL * *((int *)v6 + 1), v13, v5);
              v119 = *(_WORD *)(v118 + 20);
              v3 = 0;
              if ( (v119 & 4) == 0 )
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
              v5 = v834;
              v10 = 1;
              v13 = v832;
            }
            *(_WORD *)(v118 + 20) = v119 & 0xF240 | 4;
            goto LABEL_53;
          }
          v120 = 56LL * *((int *)v6 + 1);
          *(_WORD *)(v120 + v7 + 20) = 4;
          v121 = *(int *)(v120 + v7);
          *(_QWORD *)(v120 + v7) = (int)(-1431655765 * ((__int64)&v6[-v5] >> 3));
          v122 = 3 * v121;
LABEL_219:
          v6 = (unsigned __int8 *)(v5 + 8 * v122);
          goto LABEL_196;
        }
        if ( (_DWORD)v15 != 18 )
        {
          if ( (_DWORD)v15 != 19 )
          {
            if ( (_DWORD)v15 == 20 )
            {
              v135 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
              if ( !v135 || !*(_BYTE *)(v135 + 2) )
                goto LABEL_196;
              v136 = v7 + 56LL * *((int *)v6 + 3);
              if ( (*(_WORD *)(v136 + 20) & 0x9000) == 0 )
              {
                *(_WORD *)(v136 + 20) = v10;
                goto LABEL_215;
              }
              vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 3));
              v3 = 0;
              goto LABEL_213;
            }
LABEL_225:
            v124 = *((int *)v6 + 1);
            *(_QWORD *)&v846 = 0;
            v125 = v4[15];
            v126 = 0;
            LODWORD(v840) = 0;
            v844 = 0;
            v845 = 0;
            v127 = *(_QWORD *)(v125 + 8 * v124);
            *(_WORD *)(v127 + 2) = 0;
            *(_DWORD *)(v127 + 32) = 0;
            if ( *(_BYTE *)(v127 + 4) )
            {
              v128 = v835 + 56LL * *((int *)v6 + 3);
              v129 = *(_WORD *)(v128 + 20);
              if ( (v129 & 0x2E) == 2 )
                applyNumericAffinity(v128, 0);
              v130 = sqlite3VdbeIntValue(v128, v13);
              v131 = *(_WORD *)(v128 + 20);
              v132 = v130;
              *(_WORD *)(v128 + 20) = v129;
              if ( (v131 & 0x24) == 0 )
              {
                if ( (v131 & 8) == 0 )
                {
                  v3 = 0;
                  if ( (v131 & 1) != 0 || (unsigned int)v15 >= 0x17 )
                  {
                    v14 = Table;
                    goto LABEL_1218;
                  }
                  v133 = *(_BYTE **)(v127 + 48);
                  if ( !*v133 && (v133[1] & 8) != 0 )
                  {
                    v134 = 0;
                    Table = 0;
                    v14 = 0;
                    goto LABEL_278;
                  }
                  v153 = btreeLast(v133, &v840);
                  v3 = 0;
                  Table = v153;
                  v14 = v153;
                  if ( v153 )
                    goto LABEL_1545;
                  goto LABEL_277;
                }
                v154 = sqlite3IntFloatCompare(v130);
                if ( v154 <= 0 )
                {
                  if ( v154 < 0 && (v15 & 1) != 0 )
                    LODWORD(v15) = v15 + 1;
                }
                else if ( (v15 & 1) == 0 )
                {
                  LODWORD(v15) = v15 - 1;
                }
              }
              v155 = (_QWORD *)(v127 + 48);
              v156 = sqlite3BtreeTableMoveto(*(_QWORD *)(v127 + 48), v132, 0, &v840);
              v3 = 0;
              *(_QWORD *)(v127 + 80) = v132;
              Table = v156;
              v14 = v156;
              if ( v156 )
                goto LABEL_1545;
            }
            else
            {
              v155 = (_QWORD *)(v127 + 48);
              v157 = *(_BYTE *)(*(_QWORD *)(v127 + 48) + 3LL) & 2;
              *(_QWORD *)&v844 = *(_QWORD *)(v127 + 56);
              LOBYTE(v126) = v157 != 0;
              WORD6(v845) = *((_WORD *)v6 + 8);
              BYTE2(v846) = 0;
              v158 = *((int *)v6 + 3);
              BYTE14(v845) = v10 + (((unsigned __int8)v10 & (unsigned __int8)(v15 - 1)) != 0 ? 0xFE : 0);
              *((_QWORD *)&v844 + 1) = v835 + 56 * v158;
              v159 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v127 + 48), &v844, &v840);
              v3 = 0;
              Table = v159;
              v14 = v159;
              if ( v159 )
                goto LABEL_1545;
              if ( v157 )
              {
                if ( !BYTE2(v846) )
                  goto LABEL_277;
              }
              else
              {
                v126 = 0;
              }
            }
            if ( (int)v15 < 23 )
            {
              if ( (int)v840 <= 0 && ((_DWORD)v840 || (_DWORD)v15 != 21) )
              {
                v134 = *(_BYTE *)*v155 != 0;
                goto LABEL_278;
              }
              LODWORD(v840) = 0;
              v160 = sqlite3BtreePrevious(*v155, 0);
            }
            else
            {
              if ( (int)v840 >= 0 && ((_DWORD)v840 || (_DWORD)v15 != 24) )
              {
LABEL_279:
                v4 = a1;
                v7 = v835;
                v13 = v832;
                v10 = 1;
                if ( v126 )
                  v6 += 24;
                goto LABEL_623;
              }
              LODWORD(v840) = 0;
              v160 = sqlite3BtreeNext(*v155, 0);
            }
            v3 = 0;
            Table = v160;
            v14 = v160;
            if ( v160 )
            {
              if ( v160 != 101 )
                goto LABEL_1545;
              v14 = 0;
              Table = 0;
              v134 = 1;
LABEL_278:
              if ( !v134 )
                goto LABEL_279;
LABEL_1218:
              v10 = 1;
              goto LABEL_1219;
            }
LABEL_277:
            v134 = (int)v840;
            goto LABEL_278;
          }
          v137 = v7 + 56LL * *((int *)v6 + 2);
          if ( ((unsigned __int8)v10 & *(_BYTE *)(v7 + 56LL * *((int *)v6 + 1) + 20)) == 0 )
          {
            v138 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), 0);
            v3 = 0;
            if ( (*(_WORD *)(v137 + 20) & 0x9000) != 0 )
            {
              v139 = v138 == 0;
              v140 = v137;
LABEL_243:
              vdbeReleaseAndSetInt64(v140, v139);
              goto LABEL_244;
            }
            *(_QWORD *)v137 = v138 == 0;
            *(_WORD *)(v137 + 20) = 4;
LABEL_951:
            v5 = v834;
            v13 = v832;
LABEL_952:
            v10 = 1;
            goto LABEL_53;
          }
          if ( (*(_WORD *)(v137 + 20) & 0x9000) == 0 )
          {
            *(_WORD *)(v137 + 20) = v10;
            goto LABEL_202;
          }
          v141 = v7 + 56LL * *((int *)v6 + 2);
LABEL_248:
          vdbeMemClearExternAndSetNull(v141);
          goto LABEL_244;
        }
        if ( *((int *)v6 + 1) < 0 )
        {
          LOBYTE(v145) = *((_BYTE *)qword_1802E0640 + (*(_WORD *)(56LL * *((int *)v6 + 3) + v7 + 20) & 0x3F));
        }
        else
        {
          v142 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          if ( *((_DWORD *)v6 + 3) < (int)*(unsigned __int16 *)(v142 + 74) )
          {
            v143 = *(unsigned int *)(v142 + 4LL * *((int *)v6 + 3) + 120);
            if ( (unsigned int)v143 < 0xC )
              v144 = *((unsigned __int8 *)&qword_1802E0B88[1] + v143);
            else
              v144 = ((unsigned __int8)v10 & (unsigned __int8)v143) != 0 ? 4 : 8;
            goto LABEL_258;
          }
          v145 = *((_DWORD *)v6 + 4);
        }
        v144 = (_WORD)v10 << (v145 - v10);
LABEL_258:
        v146 = ((unsigned __int16)v144 & *((_WORD *)v6 + 1)) == 0;
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
              v147 = *((int *)v6 + 1);
              *(_QWORD *)&v846 = 0;
              v148 = v4[15];
              v844 = 0;
              v845 = 0;
              v149 = *(_QWORD *)(v148 + 8 * v147);
              v150 = v7 + 56LL * *((int *)v6 + 3);
              WORD6(v845) = *((_WORD *)v6 + 8);
              *((_QWORD *)&v844 + 1) = v150;
              if ( WORD6(v845) )
              {
                v151 = (int *)(v149 + 36);
                *(_QWORD *)&v844 = *(_QWORD *)(v149 + 56);
                BYTE14(v845) = 0;
                v14 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v149 + 48), &v844, v149 + 36);
                Table = v14;
              }
              else
              {
                if ( (*(_WORD *)(v150 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v150) )
                  goto LABEL_1543;
                v175 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v149 + 56));
                v176 = v175;
                if ( !v175 )
                  goto LABEL_1543;
                sqlite3VdbeRecordUnpack(
                  *(_QWORD *)(v149 + 56),
                  *(unsigned int *)(*((_QWORD *)&v844 + 1) + 16LL),
                  *(_QWORD *)(*((_QWORD *)&v844 + 1) + 8LL),
                  v175);
                *(_BYTE *)(v176 + 30) = 0;
                v151 = (int *)(v149 + 36);
                Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v149 + 48), v176, v149 + 36);
                v14 = Table;
                sqlite3DbFreeNN(v2, v176);
                v9 = v831;
              }
              v3 = 0;
              if ( v14 )
                goto LABEL_1546;
              v177 = *v151;
              *(_BYTE *)(v149 + 3) = 0;
              *(_DWORD *)(v149 + 32) = 0;
              *(_BYTE *)(v149 + 2) = v177 != 0;
              if ( *v6 == 29 )
              {
                v10 = 1;
                if ( !v177 )
                  goto LABEL_1219;
LABEL_335:
                v7 = v835;
                goto LABEL_195;
              }
              if ( v177 )
                goto LABEL_1218;
              v10 = 1;
              if ( *v6 == 27 )
              {
                v178 = 0;
                if ( !WORD6(v845) )
                  goto LABEL_1403;
                while ( (*(_BYTE *)(56LL * v178 + *((_QWORD *)&v844 + 1) + 20) & 1) == 0 )
                {
                  if ( (int)++v178 >= WORD6(v845) )
                    goto LABEL_335;
                }
                goto LABEL_1219;
              }
              v7 = v835;
              v13 = v832;
              if ( *v6 == 26 )
              {
                *(_WORD *)(v149 + 12) = *((_WORD *)v6 + 8);
                goto LABEL_1078;
              }
LABEL_623:
              v5 = v834;
LABEL_978:
              v9 = v831;
              goto LABEL_53;
            }
            v152 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            if ( v152 && !*(_BYTE *)(v152 + 2) )
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
              v167 = 56LL * *((int *)v6 + 3);
              v849 = 0;
              if ( (*(_BYTE *)(v167 + v7 + 20) & 0x24) == 0 )
              {
                LOBYTE(v5) = v9;
                LOBYTE(v13) = 67;
                v168 = *(_OWORD *)(v167 + v7 + 16);
                v853 = *(_OWORD *)(v167 + v7);
                v169 = *(_OWORD *)(v167 + v7 + 32);
                v854 = v168;
                *(_QWORD *)&v168 = *(_QWORD *)(v167 + v7 + 48);
                v855 = v169;
                v856 = v168;
                applyAffinity(&v853, v13, v5);
                v3 = 0;
                if ( (BYTE4(v854) & 4) == 0 )
                  goto LABEL_1218;
                v170 = v853;
                goto LABEL_322;
              }
              break;
            case 0x1F:
              break;
            case 0x20:
LABEL_1211:
              v643 = *((int *)v6 + 1);
              v644 = v4[15];
              LODWORD(v838) = 0;
              v645 = *(_QWORD *)(v644 + 8 * v643);
              v646 = *(_QWORD *)(v645 + 48);
              if ( (_BYTE)v15 == 0x89 )
              {
                v647 = *(_QWORD *)(v645 + 48);
                *(_DWORD *)(v645 + 36) = -1;
                IsValidNN = sqlite3BtreeCursorIsValidNN(v647);
                v3 = 0;
                if ( IsValidNN )
                  goto LABEL_1407;
              }
              v649 = sqlite3BtreeLast(v646, &v838);
              v3 = 0;
              Table = v649;
              v14 = v649;
              *(_BYTE *)(v645 + 2) = v838;
              *(_BYTE *)(v645 + 3) = 0;
              *(_DWORD *)(v645 + 32) = 0;
              if ( v649 )
                goto LABEL_1546;
              if ( *((int *)v6 + 2) <= 0 )
                goto LABEL_1407;
              if ( (_DWORD)v838 )
                goto LABEL_1218;
              goto LABEL_79;
            default:
              v161 = *((int *)v6 + 1);
              v162 = v4[15];
              LODWORD(v838) = 0;
              v163 = *(_QWORD *)(*(_QWORD *)(v162 + 8 * v161) + 48LL);
              v164 = sqlite3BtreeFirst(v163, &v838);
              v3 = 0;
              Table = v164;
              v14 = v164;
              if ( v164 )
                goto LABEL_1546;
              if ( (_DWORD)v838 )
              {
                v165 = -1;
              }
              else
              {
                v166 = sqlite3BtreeRowCountEst(v163);
                v165 = (__int16)sqlite3LogEst(v166);
                v3 = 0;
              }
              v10 = 1;
              if ( v165 < *((int *)v6 + 3) )
                goto LABEL_1404;
              if ( v165 > *((int *)v6 + 4) )
                goto LABEL_195;
              goto LABEL_1219;
          }
          v170 = *(_QWORD *)(56LL * *((int *)v6 + 3) + v7);
LABEL_322:
          v171 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v172 = *(_QWORD *)(v171 + 48);
          v849 = 0;
          v173 = sqlite3BtreeTableMoveto(v172, v170, 0, &v849);
          v3 = 0;
          *(_QWORD *)(v171 + 80) = v170;
          *(_WORD *)(v171 + 2) = 0;
          v14 = v173;
          *(_DWORD *)(v171 + 32) = 0;
          Table = v173;
          *(_DWORD *)(v171 + 36) = v849;
          if ( v849 )
          {
            if ( *((_DWORD *)v6 + 2) )
              goto LABEL_1218;
            v14 = sqlite3CorruptError(98564);
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
          v189 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), 2);
          v190 = sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 2), 2);
          v10 = 1;
          v191 = v190 + 2 * v189 + v189;
          v192 = &qword_1802DC2F8;
          if ( *v6 != 44 )
            v192 = qword_1802DD780;
          v193 = *((unsigned __int8 *)v192 + v191);
          v194 = 56LL * *((int *)v6 + 3);
          v195 = *(_WORD *)(v194 + v7 + 20);
          if ( (_BYTE)v193 == 2 )
          {
            v196 = v195 & 0xF240 | 1;
          }
          else
          {
            *(_QWORD *)(v194 + v7) = v193;
            v196 = v195 & 0xF240 | 4;
          }
          *(_WORD *)(v194 + v7 + 20) = v196;
          goto LABEL_60;
        }
      }
      else if ( (_DWORD)v15 != 40 )
      {
        v179 = v15 - 35;
        if ( !v179 )
        {
LABEL_358:
          *((_DWORD *)v4 + 55) += v10;
          goto LABEL_359;
        }
        v180 = v179 - 1;
        if ( !v180 )
        {
LABEL_359:
          v185 = *((int *)v6 + 1);
          v186 = v4[15];
          LODWORD(v840) = 0;
          v187 = *(_QWORD *)(v186 + 8 * v185);
          LODWORD(v840) = v10;
          if ( *(_BYTE *)v187 == (_BYTE)v10 )
          {
            v188 = sqlite3VdbeSorterRewind(v187, &v840);
            v3 = 0;
          }
          else
          {
            v188 = sqlite3BtreeFirst(*(_QWORD *)(v187 + 48), &v840);
            v3 = 0;
            *(_BYTE *)(v187 + 3) = 0;
            *(_DWORD *)(v187 + 32) = 0;
          }
          Table = v188;
          v14 = v188;
          if ( v188 )
            goto LABEL_1546;
          *(_BYTE *)(v187 + 2) = (_BYTE)v840;
          if ( *((int *)v6 + 2) <= 0 )
            goto LABEL_1408;
          v109 = (_DWORD)v840 == 0;
LABEL_194:
          v10 = 1;
          if ( v109 )
          {
LABEL_195:
            v5 = v834;
            goto LABEL_196;
          }
LABEL_1219:
          v9 = v831;
          goto LABEL_214;
        }
        v181 = v180 - 1;
        if ( v181 )
        {
          v182 = v181 - 1;
          if ( v182 )
          {
            if ( v182 != 1 )
              goto LABEL_53;
            v183 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v184 = sqlite3BtreeNext(*(_QWORD *)(v183 + 48), *((unsigned int *)v6 + 3));
          }
          else
          {
            v183 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
            v184 = sqlite3BtreePrevious(*(_QWORD *)(v183 + 48), *((unsigned int *)v6 + 3));
          }
        }
        else
        {
          v183 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
          v184 = sqlite3VdbeSorterNext(v2, v183);
        }
        v14 = v184;
        Table = v184;
        v3 = 0;
        *(_DWORD *)(v183 + 32) = 0;
        if ( !v184 )
        {
          *(_BYTE *)(v183 + 2) = 0;
          v10 = 1;
          ++*((_DWORD *)v4 + *((unsigned __int16 *)v6 + 1) + 53);
LABEL_503:
          v5 = v834;
          goto LABEL_504;
        }
        if ( v184 != 101 )
          goto LABEL_1546;
        v10 = 1;
        Table = 0;
        *(_BYTE *)(v183 + 2) = 1;
        v14 = 0;
LABEL_1310:
        if ( *(_DWORD *)(v2 + 408) )
        {
LABEL_1536:
          v14 = 9;
          goto LABEL_1546;
        }
        v721 = v851;
        if ( v852 >= v851 )
        {
          while ( 1 )
          {
            v722 = *(__int64 (__fastcall **)(_QWORD))(v2 + 528);
            if ( !v722 )
              goto LABEL_1407;
            v723 = *(unsigned int *)(v2 + 544);
            v724 = v722(*(_QWORD *)(v2 + 536));
            v3 = 0;
            if ( v724 )
              goto LABEL_1535;
            v721 += v723;
            v851 = v721;
            if ( v852 < v721 )
              goto LABEL_51;
          }
        }
LABEL_1403:
        v7 = v835;
LABEL_1404:
        v13 = v832;
        goto LABEL_623;
      }
    }
    v197 = *((int *)v6 + 1);
    *(_QWORD *)&v846 = 0;
    v198 = v4[15];
    v844 = 0;
    v845 = 0;
    v199 = *(_QWORD *)(v198 + 8 * v197);
    v853 = 0;
    v854 = 0;
    *(_QWORD *)&v844 = *(_QWORD *)(v199 + 56);
    WORD6(v845) = *((_WORD *)v6 + 8);
    BYTE14(v845) = -((unsigned __int8)v15 < 0x2Au);
    v200 = 56LL * *((int *)v6 + 3);
    v855 = 0;
    v856 = 0;
    *((_QWORD *)&v844 + 1) = v7 + v200;
    v201 = *(_QWORD *)(v199 + 48);
    v202 = sqlite3BtreePayloadSize(v201);
    if ( v202 - 1 <= 0x7FFFFFFE )
    {
      sqlite3VdbeMemInit(&v853, v2, 0);
      v203 = sqlite3VdbeMemFromBtreeZeroOffset(v201, v202, &v853);
      v3 = 0;
      Table = v203;
      v14 = v203;
      if ( v203 )
        goto LABEL_1546;
      v204 = sqlite3VdbeRecordCompareWithSkip((unsigned int)v854, *((_QWORD *)&v853 + 1), &v844, 0);
      sqlite3VdbeMemReleaseMalloc(&v853);
      v205 = v204 + 1;
      v3 = 0;
      v206 = -v204;
      v10 = 1;
      if ( (*v6 & 1) != 0 )
        v206 = v205;
      if ( v206 <= 0 )
        goto LABEL_146;
      goto LABEL_1219;
    }
    v820 = sqlite3CorruptError(99861);
LABEL_1530:
    v14 = v820;
    goto LABEL_1523;
  }
  if ( (unsigned int)v15 <= 0x44 )
  {
    if ( (_DWORD)v15 == 68 )
    {
      v280 = 56LL * *((int *)v6 + 1);
      v281 = 3LL * *(_QWORD *)(v280 + v7);
      *(_QWORD *)(v280 + v7) = (int)(-1431655765 * ((__int64)&v6[-v4[17]] >> 3) - v10);
      v122 = 3LL * (*(_DWORD *)(v5 + 8 * v281 + 8) - (int)v10);
      goto LABEL_219;
    }
    if ( (unsigned int)v15 > 0x39 )
    {
      if ( (unsigned int)v15 > 0x3F )
      {
        v266 = v15 - 64;
        if ( !v266 )
        {
          v275 = 56LL * *((int *)v6 + 1);
          v276 = filterHash(v7, v6);
          v10 = 1;
          v277 = v276 % (8 * *(_DWORD *)(v275 + v7 + 16));
          v278 = *(char *)((v277 >> 3) + *(_QWORD *)(v275 + v7 + 8));
          v279 = _bittest(&v278, v277 & 7);
          v5 = v834;
          if ( v279 )
          {
            ++*((_DWORD *)v4 + 60);
            goto LABEL_61;
          }
          ++*((_DWORD *)v4 + 61);
          v3 = 0;
          goto LABEL_215;
        }
        v267 = v266 - 1;
        if ( v267 )
        {
          v268 = v267 - 1;
          if ( v268 )
          {
            if ( v268 != 1 )
              goto LABEL_53;
            v269 = 56LL * *((int *)v6 + 1);
            if ( (*(_BYTE *)(v269 + v7 + 20) & 4) == 0 )
              goto LABEL_53;
            v117 = *(_QWORD *)(v269 + v7);
            goto LABEL_206;
          }
        }
        v270 = *((_QWORD *)v6 + 2);
        v271 = v7 + 56LL * *((int *)v6 + 3);
        if ( *(_QWORD *)v270 != v271 )
        {
          v272 = *(unsigned __int8 *)(v270 + 42);
          *(_BYTE *)(v270 + 40) = v831;
          *(_QWORD *)(v270 + 24) = v4;
          *(_QWORD *)v270 = v271;
          while ( 1 )
          {
            v272 -= v10;
            if ( v272 < 0 )
              break;
            *(_QWORD *)(v270 + 8LL * (unsigned int)v272 + 48) = v7 + 56LL * (v272 + *((_DWORD *)v6 + 2));
          }
        }
        *(_WORD *)(v271 + 20) &= 0xF241u;
        *(_WORD *)(v271 + 20) |= v10;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v270 + 8) + 24LL))(
          v270,
          *(unsigned __int8 *)(v270 + 42),
          v270 + 48);
        v273 = *(_DWORD *)(v270 + 36);
        v3 = 0;
        if ( !v273 )
          goto LABEL_1408;
        if ( v273 > 0 )
        {
          v274 = (const char *)sqlite3_value_text(v271);
          sqlite3VdbeError(v4, "%s", v274);
          v14 = *(_DWORD *)(v270 + 36);
          Table = v14;
        }
        sqlite3VdbeDeleteAuxData(v2, v4 + 37, *(unsigned int *)(v270 + 32), *((unsigned int *)v6 + 1));
        v3 = 0;
        *(_DWORD *)(v270 + 36) = 0;
LABEL_325:
        v174 = v14 == 0;
        goto LABEL_326;
      }
      if ( (_DWORD)v15 != 63 )
      {
        v249 = v15 - 58;
        if ( v249 )
        {
          v250 = v249 - 1;
          if ( !v250 )
          {
            v259 = 56LL * *((int *)v6 + 1);
            v260 = *(_QWORD *)(v259 + v7);
            if ( v260 <= 0 )
              goto LABEL_196;
            *(_QWORD *)(v259 + v7) = v260 - *((int *)v6 + 3);
            goto LABEL_215;
          }
          v251 = v250 - 1;
          if ( !v251 )
          {
            v257 = 56LL * *((int *)v6 + 1);
            v258 = *(_QWORD *)(v257 + v7);
            if ( !v258 )
              goto LABEL_53;
            if ( v258 > 0 )
              *(_QWORD *)(v257 + v7) = v258 - 1;
            goto LABEL_215;
          }
          v252 = v251 - 1;
          if ( !v252 )
          {
            v254 = 56LL * *((int *)v6 + 1);
            v255 = *(_QWORD *)(v254 + v7);
            if ( v255 == 0x8000000000000000uLL )
              goto LABEL_53;
            v256 = v255 - 1;
            *(_QWORD *)(v254 + v7) = v256;
            if ( v256 )
              goto LABEL_53;
            goto LABEL_1219;
          }
          if ( v252 != 1 )
            goto LABEL_53;
          v253 = sqlite3BtreeIncrVacuum(*(_QWORD *)(32LL * *((int *)v6 + 1) + *(_QWORD *)(v2 + 32) + 8));
          v3 = 0;
          Table = v253;
          v14 = v253;
          if ( !v253 )
            goto LABEL_1408;
          if ( v253 != 101 )
            goto LABEL_1546;
          v14 = 0;
          Table = 0;
          goto LABEL_213;
        }
        v212 = (_DWORD)v13 == 0;
        goto LABEL_497;
      }
      v261 = *(_QWORD *)(v4[15] + 8LL * *((int *)v6 + 1));
      if ( *(_BYTE *)(v261 + 2) )
        goto LABEL_148;
      v262 = *(__int64 ***)(v261 + 48);
      v263 = *v262;
      v264 = **v262;
      Table = (*(__int64 (**)(void))(v264 + 72))();
      v14 = Table;
      sqlite3VtabImportErrmsg(v4, v263);
      v3 = 0;
      if ( Table )
        goto LABEL_1546;
      v265 = (*(__int64 (__fastcall **)(_QWORD))(v264 + 80))(*(_QWORD *)(v261 + 48));
      v9 = v831;
      v3 = 0;
      if ( v265 )
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
        v207 = v15 - 46;
        if ( v207 )
        {
          v208 = v207 - 1;
          if ( v208 )
          {
            v209 = v208 - 1;
            if ( v209 )
            {
              v210 = v209 - 1;
              if ( v210 )
              {
                if ( v210 != 1 )
                  goto LABEL_53;
                v146 = ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 1) + v7 + 20)) == 0;
LABEL_259:
                if ( v146 )
                  goto LABEL_53;
                goto LABEL_215;
              }
              if ( *((_DWORD *)v6 + 1) )
                v211 = *(_QWORD *)(v2 + 760) == 0;
              else
                v211 = v4[10] == 0;
              if ( !v211 )
                goto LABEL_53;
              v212 = *(_QWORD *)(v2 + 768) == 0;
LABEL_497:
              if ( !v212 )
                goto LABEL_53;
              goto LABEL_215;
            }
            v213 = *((_QWORD *)v6 + 2);
            v837 = (unsigned int *)v213;
            if ( *((_WORD *)v6 + 1) )
            {
              for ( jj = v4[33]; jj; jj = *(_QWORD *)(jj + 8) )
              {
                if ( *(_QWORD *)(jj + 48) == *(_QWORD *)(v213 + 32) )
                  goto LABEL_202;
              }
            }
            if ( *((_DWORD *)v4 + 70) >= *(_DWORD *)(v2 + 176) )
            {
              v14 = v10;
              sqlite3VdbeError(v4, "too many levels of trigger recursion");
              goto LABEL_1523;
            }
            v215 = (int *)(v213 + 16);
            v216 = (int *)(v213 + 8);
            v217 = 56LL * *((int *)v6 + 3) + v7;
            if ( (*(_BYTE *)(v217 + 20) & 0x10) != 0 )
            {
              v220 = *(_QWORD *)(v217 + 8);
              v222 = (__int64 *)v213;
LABEL_413:
              *((_DWORD *)v4 + 70) += v10;
              *(_QWORD *)(v220 + 8) = v4[33];
              v835 = v220 + 112;
              *(_QWORD *)(v220 + 56) = *(_QWORD *)(v839 + 56);
              *(_QWORD *)(v220 + 96) = v4[7];
              *(_QWORD *)(v220 + 104) = *(_QWORD *)(*v4 + 120);
              *(_QWORD *)(v220 + 64) = v4[37];
              v4[13] = v220 + 112;
              v4[37] = 0;
              v4[7] = 0;
              v4[33] = v220;
              v225 = *(int *)(v220 + 88);
              *((_DWORD *)v4 + 9) = v225;
              *((_DWORD *)v4 + 10) = *(unsigned __int16 *)(v220 + 92);
              v4[15] = v220 + 112 + 56 * v225;
              v226 = (void *)(v220 + 112 + 8 * (*v215 + 7 * v225));
              *(_QWORD *)(v220 + 40) = v226;
              memset_0(v226, 0, (*v216 + 7) / 8);
              v227 = *v222;
              v14 = Table;
              v4[17] = *v222;
              v228 = *v216;
              v2 = v839;
              v6 = (unsigned __int8 *)(v227 - 24);
              v834 = v227;
              *((_DWORD *)v4 + 36) = v228;
LABEL_1308:
              v3 = 0;
              goto LABEL_1309;
            }
            v218 = *v215 + *(_DWORD *)(v213 + 12) + 1;
            if ( *v215 )
              v218 = *v215 + *(_DWORD *)(v213 + 12);
            v219 = (*v216 + 7) / 8 + 8 * (*v215 + 7 * (v218 + 2));
            v220 = sqlite3DbMallocZero(v839, v219);
            if ( v220 )
            {
              sqlite3VdbeMemRelease(v217);
              *(_QWORD *)(v217 + 48) = sqlite3VdbeFrameMemDel;
              v221 = v220 + 112;
              *(_DWORD *)(v217 + 16) = v219;
              v4 = a1;
              *(_WORD *)(v217 + 20) = 4112;
              *(_QWORD *)(v217 + 8) = v220;
              v222 = (__int64 *)v837;
              *(_QWORD *)v220 = a1;
              *(_DWORD *)(v220 + 88) = v218;
              *(_DWORD *)(v220 + 92) = *v215;
              *(_DWORD *)(v220 + 76) = -1431655765 * ((__int64)&v6[-v834] >> 3);
              *(_QWORD *)(v220 + 24) = a1[13];
              *(_DWORD *)(v220 + 84) = *((_DWORD *)a1 + 9);
              *(_QWORD *)(v220 + 32) = a1[15];
              *(_DWORD *)(v220 + 72) = *((_DWORD *)a1 + 10);
              *(_QWORD *)(v220 + 16) = a1[17];
              *(_DWORD *)(v220 + 80) = *((_DWORD *)a1 + 36);
              *(_QWORD *)(v220 + 48) = v222[4];
              v223 = v220 + 56 * (v218 + 2LL);
              if ( v220 + 112 != v223 )
              {
                v224 = v839;
                do
                {
                  *(_WORD *)(v221 + 20) = 0;
                  *(_QWORD *)(v221 + 24) = v224;
                  v221 += 56;
                }
                while ( v221 != v223 );
                v4 = a1;
              }
              v9 = v831;
              LODWORD(v10) = 1;
              goto LABEL_413;
            }
            goto LABEL_1541;
          }
          v229 = *((_DWORD *)v6 + 4);
          v230 = v7 + 56LL * *((int *)v6 + 1);
          v231 = *((int *)v6 + 3);
          if ( (*(_BYTE *)(v230 + 20) & 0x10) == 0 )
          {
            v232 = sqlite3VdbeMemSetRowSet(v230);
            v3 = 0;
            if ( v232 )
              goto LABEL_1543;
          }
          v233 = 56 * v231;
          v234 = v229 < 0;
          if ( v229 )
          {
            v235 = sqlite3RowSetTest(*(_QWORD *)(v230 + 8), (unsigned int)v229, *(_QWORD *)(v233 + v835));
            v3 = 0;
            if ( v235 )
              goto LABEL_1218;
            v234 = v229 < 0;
          }
          if ( v234 )
          {
LABEL_79:
            v7 = v835;
            goto LABEL_80;
          }
          sqlite3RowSetInsert(*(_QWORD *)(v230 + 8), *(_QWORD *)(v233 + v835));
LABEL_421:
          v7 = v835;
          goto LABEL_422;
        }
        v236 = *((int *)v6 + 1);
        v837 = 0;
        v237 = v7 + 56 * v236;
        if ( (*(_BYTE *)(v237 + 20) & 0x10) != 0 && (unsigned int)sqlite3RowSetNext(*(_QWORD *)(v237 + 8), &v837) )
        {
          sqlite3VdbeMemSetInt64(v7 + 56LL * *((int *)v6 + 3), v837);
          goto LABEL_1308;
        }
        sqlite3VdbeMemSetNull(v237);
        v3 = 0;
LABEL_502:
        v10 = 1;
        goto LABEL_503;
      }
      if ( (_DWORD)v15 != 52 && (_DWORD)v15 != 53 && (_DWORD)v15 != 54 && (unsigned int)(v15 - 55) > 1 )
        goto LABEL_53;
    }
    v238 = v7 + 56LL * *((int *)v6 + 1);
    v239 = v7 + 56LL * *((int *)v6 + 3);
    v240 = *(_WORD *)(v238 + 20);
    v241 = *(_WORD *)(v239 + 20);
    if ( ((unsigned __int8)v240 & (unsigned __int8)v241 & 4) != 0 )
    {
      if ( *(_QWORD *)v239 <= *(_QWORD *)v238 )
      {
        v243 = *v6;
        v9 = v831;
        if ( *(_QWORD *)v239 >= *(_QWORD *)v238 )
        {
          if ( *((_BYTE *)&qword_1802DDC20[26] + v243 + 2) )
            goto LABEL_215;
          v13 = 0;
        }
        else
        {
          if ( *((_BYTE *)&qword_1802DDC20[25] + v243 + 4) )
            goto LABEL_215;
          v13 = 0xFFFFFFFFLL;
        }
        goto LABEL_438;
      }
      v242 = *((_BYTE *)&qword_1802DDC20[27] + v15) == 0;
LABEL_436:
      v9 = v831;
      if ( !v242 )
        goto LABEL_215;
      v13 = (unsigned int)v10;
LABEL_438:
      v4 = a1;
      v7 = v835;
      v832 = v13;
      goto LABEL_53;
    }
    v244 = v240 | v241;
    if ( ((unsigned __int8)(v240 | v241) & (unsigned __int8)v10) != 0 )
    {
      if ( (v6[2] & 0x80u) == 0 )
      {
        v242 = (v6[2] & 0x10) == 0;
        goto LABEL_436;
      }
      if ( ((unsigned __int8)(v240 & v241) & (unsigned __int8)v10) != 0 && (v241 & 0x100) == 0 )
      {
        v13 = 0;
LABEL_449:
        v832 = v13;
LABEL_450:
        v245 = *v6;
        if ( (_DWORD)v13 )
          v246 = *((_BYTE *)&qword_1802DDC20[27] + v245);
        else
          v246 = *((_BYTE *)&qword_1802DDC20[26] + v245 + 2);
LABEL_476:
        *(_WORD *)(v239 + 20) = v241;
        *(_WORD *)(v238 + 20) = v240;
        if ( !v246 )
        {
          v4 = a1;
          v7 = v835;
          goto LABEL_148;
        }
        goto LABEL_1219;
      }
      if ( ((unsigned __int8)v241 & (unsigned __int8)v10) == 0 )
      {
        v13 = (unsigned int)v10;
        goto LABEL_449;
      }
      v13 = 0xFFFFFFFFLL;
      v832 = -1;
    }
    else
    {
      v247 = v6[2] & 0x47;
      if ( v247 < 0x43u )
      {
        if ( v247 == 66 && (v244 & 2) != 0 )
        {
          if ( (v240 & 2) != 0 )
          {
            *(_WORD *)(v238 + 20) = v240 & 0xFFD3;
          }
          else if ( (v240 & 0x2C) != 0 )
          {
            LOBYTE(v5) = v10;
            LOBYTE(v13) = v831;
            sqlite3VdbeMemStringify(v238, v13, v5);
            v240 = *(_WORD *)(v238 + 20) ^ (*(_WORD *)(v238 + 20) ^ v240) & 0xDBF;
            LOBYTE(v10) = 1;
            if ( v238 == v239 )
              v241 = v240 | 2;
          }
          if ( (v241 & 2) != 0 )
          {
            *(_WORD *)(v239 + 20) &= 0xFFD3u;
          }
          else if ( (v241 & 0x2C) != 0 )
          {
            LOBYTE(v5) = v10;
            LOBYTE(v13) = v831;
            sqlite3VdbeMemStringify(v239, v13, v5);
            v241 = *(_WORD *)(v239 + 20) ^ (*(_WORD *)(v239 + 20) ^ v241) & 0xDBF;
          }
        }
      }
      else if ( (v244 & 2) != 0 )
      {
        if ( (v240 & 0x2E) == 2 )
        {
          applyNumericAffinity(v238, 0);
          v241 = *(_WORD *)(v239 + 20);
        }
        if ( (v241 & 0x2E) == 2 )
          applyNumericAffinity(v239, 0);
      }
      v248 = sqlite3MemCompare(v239, v238, *((_QWORD *)v6 + 2));
      v5 = v834;
      v3 = 0;
      v832 = v248;
      v13 = (unsigned int)v248;
      v10 = 1;
      if ( v248 >= 0 )
        goto LABEL_450;
    }
    v246 = *((_BYTE *)&qword_1802DDC20[25] + *v6 + 4);
    goto LABEL_476;
  }
  if ( (unsigned int)v15 > 0x50 )
  {
    if ( (unsigned int)v15 > 0x56 )
    {
      v328 = v15 - 87;
      if ( !v328 )
      {
        if ( (*(_BYTE *)(v7 + 56LL * *((int *)v6 + 1) + 20) & 0x24) == 0 )
          goto LABEL_53;
        sqlite3VdbeMemRealify();
        goto LABEL_244;
      }
      v329 = v328 - 1;
      if ( v329 )
      {
        v330 = v329 - 2;
        if ( !v330 )
        {
          if ( ((unsigned __int8)v10 & v6[2]) != 0 )
            v331 = *((_QWORD *)v6 - 1) + 4LL;
          else
            v331 = 0;
          v332 = *((_DWORD *)v6 + 3);
          v333 = 0;
          v334 = (unsigned int *)*((_QWORD *)v6 + 2);
          v335 = *((_DWORD *)v6 + 1);
          v336 = *((_DWORD *)v6 + 2);
          v837 = v334;
          LODWORD(v838) = v332;
          v843 = v335;
          LODWORD(v840) = v336;
          if ( v332 <= 0 )
            goto LABEL_616;
          while ( 1 )
          {
            v337 = v331 ? *(_DWORD *)(v331 + 4LL * v333) : v333;
            v338 = v835 + 56LL * (unsigned int)(v337 + v336);
            v339 = (unsigned __int8)(v10 & *(_BYTE *)(*((_QWORD *)v334 + 3) + v333));
            v340 = v835 + 56LL * (v337 + v335);
            v341 = sqlite3MemCompare(v340, v338, *(_QWORD *)&v334[2 * v333 + 8]);
            v3 = 0;
            v832 = v341;
            v13 = v341;
            v10 = 1;
            if ( v341 )
              break;
            v334 = v837;
            ++v333;
            v335 = v843;
            v336 = (int)v840;
            if ( (int)v333 >= (int)v838 )
            {
              v14 = Table;
              v4 = a1;
LABEL_616:
              v7 = v835;
              v5 = v834;
              goto LABEL_148;
            }
          }
          if ( (*(_BYTE *)(v333 + *((_QWORD *)v837 + 3)) & 2) != 0
            && ((*(_BYTE *)(v340 + 20) & 1) != 0 || (*(_BYTE *)(v338 + 20) & 1) != 0) )
          {
            v13 = -v341;
            v832 = -v341;
          }
          v14 = Table;
          v4 = a1;
          v7 = v835;
          if ( v339 )
          {
            v13 = (unsigned int)-(int)v13;
            v832 = v13;
          }
          goto LABEL_623;
        }
        if ( v330 != 1 )
          goto LABEL_53;
        v139 = (int)sqlite3VdbeBooleanValue(v7 + 56LL * *((int *)v6 + 1), *((unsigned int *)v6 + 3))
             ^ (unsigned __int64)*((int *)v6 + 4);
        v323 = v7 + 56LL * *((int *)v6 + 2);
        if ( (*(_WORD *)(v323 + 20) & 0x9000) == 0 )
        {
          *(_QWORD *)v323 = v139;
          *(_WORD *)(v323 + 20) = 4;
          v3 = 0;
          goto LABEL_951;
        }
LABEL_591:
        v140 = v323;
        goto LABEL_243;
      }
      v342 = v7 + 56LL * *((int *)v6 + 1);
      if ( (*(_WORD *)(v342 + 20) & 0x400) != 0 )
      {
        v343 = sqlite3VdbeMemExpandBlob(v7 + 56LL * *((int *)v6 + 1));
        v3 = 0;
        v14 = v343;
        if ( v343 )
          goto LABEL_1546;
      }
      LOBYTE(v13) = v6[8];
      LOBYTE(v5) = v9;
      v75 = sqlite3VdbeMemCast(v342, v13, v5);
      goto LABEL_153;
    }
    if ( (_DWORD)v15 == 86 )
    {
      v327 = (_QWORD *)(v7 + 56LL * *((int *)v6 + 1));
      sqlite3VdbeMemIntegerify(v327);
      *v327 += *((int *)v6 + 2);
      goto LABEL_244;
    }
    v318 = v15 - 81;
    if ( v318 )
    {
      v319 = v318 - 1;
      if ( v319 )
      {
        v320 = v319 - 1;
        if ( v320 )
        {
          v321 = v320 - 1;
          if ( !v321 )
          {
            *((_DWORD *)v4 + 11) = v10 | (*((_DWORD *)v4 + 11) + 2);
            v4[20] = v7 + 56LL * *((int *)v6 + 1);
            if ( !*(_BYTE *)(v2 + 103) )
            {
              if ( (*(_BYTE *)(v2 + 110) & 4) != 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v2 + 248))(4, *(_QWORD *)(v2 + 256), v4, 0);
                v5 = v834;
                LODWORD(v10) = 1;
              }
              v14 = 100;
              *((_DWORD *)v4 + 12) = v10 - 1431655765 * ((__int64)&v6[-v5] >> 3);
              goto LABEL_1564;
            }
            goto LABEL_1543;
          }
          if ( v321 != 1 || !*((_DWORD *)v6 + 1) )
            goto LABEL_53;
          v322 = *((int *)v6 + 1);
LABEL_589:
          v323 = v7 + 56 * v322;
          if ( (*(_WORD *)(v323 + 20) & 0x9000) == 0 )
          {
            *(_QWORD *)v323 = 0;
            *(_WORD *)(v323 + 20) = 4;
            goto LABEL_53;
          }
          v139 = 0;
          goto LABEL_591;
        }
        v75 = sqlite3VdbeCheckFk(v4, 0);
LABEL_153:
        v3 = 0;
        Table = v75;
        v76 = v75 == 0;
        v14 = v75;
        goto LABEL_154;
      }
      v324 = v7 + 56LL * *((int *)v6 + 2);
      if ( (*(_WORD *)(v324 + 20) & 0x9000) != 0 )
      {
        v139 = *(_QWORD *)(56LL * *((int *)v6 + 1) + v7);
        v140 = v7 + 56LL * *((int *)v6 + 2);
        goto LABEL_243;
      }
      *(_QWORD *)v324 = *(_QWORD *)(56LL * *((int *)v6 + 1) + v7);
      *(_WORD *)(v324 + 20) = 4;
LABEL_1078:
      v5 = v834;
      goto LABEL_53;
    }
    v325 = v7 + 56LL * *((int *)v6 + 1);
    v326 = v7 + 56LL * *((int *)v6 + 2);
LABEL_598:
    sqlite3VdbeMemShallowCopy(v326, v325, 0x4000);
    goto LABEL_244;
  }
  if ( (_DWORD)v15 == 80 )
  {
    v313 = *((_DWORD *)v6 + 3);
    v314 = v835 + 56LL * *((int *)v6 + 1);
    for ( kk = v835 + 56LL * *((int *)v6 + 2); ; kk += 56 )
    {
      sqlite3VdbeMemShallowCopy(kk, v314, 0x4000);
      if ( (*(_WORD *)(kk + 20) & 0x4000) != 0 )
      {
        v316 = sqlite3VdbeMemMakeWriteable(kk);
        v3 = 0;
        if ( v316 )
          goto LABEL_1543;
      }
      else
      {
        v3 = 0;
      }
      v317 = *(_WORD *)(kk + 20);
      if ( (v317 & 0x800) != 0 && (v6[2] & 2) != 0 )
        *(_WORD *)(kk + 20) = v317 & 0xF7FF;
      if ( !v313 )
        break;
      --v313;
      v314 += 56;
    }
    goto LABEL_1407;
  }
  if ( (unsigned int)v15 > 0x4A )
  {
    v293 = v15 - 75;
    if ( v293 )
    {
      v294 = v293 - 1;
      if ( !v294 )
      {
        v308 = 56LL * *((int *)v6 + 1);
        *(_WORD *)(v308 + v7 + 20) &= 0xFFC1u;
        *(_WORD *)(v308 + v7 + 20) |= v10;
        goto LABEL_53;
      }
      v295 = v294 - 1;
      if ( v295 )
      {
        v296 = v295 - 1;
        if ( v296 )
        {
          if ( v296 != 1 )
            goto LABEL_53;
          v297 = *((_DWORD *)v6 + 3);
          v298 = v835 + 56LL * *((int *)v6 + 1);
          v299 = v835 + 56LL * *((int *)v6 + 2);
          while ( 1 )
          {
            sqlite3VdbeMemMove(v299, v298);
            if ( (*(_WORD *)(v299 + 20) & 0x4000) != 0 )
            {
              v300 = sqlite3VdbeMemMakeWriteable(v299);
              v3 = 0;
              if ( v300 )
                goto LABEL_1543;
            }
            else
            {
              v3 = 0;
            }
            v298 += 56;
            v299 += 56;
            v10 = 1;
            if ( !--v297 )
              goto LABEL_145;
          }
        }
        v301 = 56LL * *((int *)v6 + 1) - 56 + v4[16];
        v302 = sqlite3VdbeMemTooBig(v301);
        v3 = 0;
        if ( v302 )
          goto LABEL_1528;
        v303 = v7 + 56LL * *((int *)v6 + 2);
        if ( (*(_WORD *)(v303 + 20) & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v7 + 56LL * *((int *)v6 + 2));
          v3 = 0;
        }
        *(_OWORD *)v303 = *(_OWORD *)v301;
        *(_QWORD *)(v303 + 16) = *(_QWORD *)(v301 + 16);
        *(_WORD *)(v303 + 20) = *(_WORD *)(v303 + 20) & 0x8FBF | 0x2040;
        goto LABEL_80;
      }
      v304 = out2Prerelease(v4, v6);
      v305 = *((_QWORD *)v6 + 2);
      v306 = v304;
      if ( v305 )
      {
        sqlite3VdbeMemSetStr(v304, v305, *((int *)v6 + 1), 0, 0);
        v3 = 0;
      }
      else
      {
        sqlite3VdbeMemSetZeroBlob(v304, *((unsigned int *)v6 + 1));
        v307 = sqlite3VdbeMemExpandBlob(v306);
        v3 = 0;
        if ( v307 )
          goto LABEL_1543;
      }
      *(_BYTE *)(v306 + 22) = v9;
      goto LABEL_52;
    }
LABEL_565:
    v309 = out2Prerelease(v4, v6);
    v310 = *((_DWORD *)v6 + 3) - *((_DWORD *)v6 + 2);
    v10 = 1;
    v3 = 0;
    v311 = *((_DWORD *)v6 + 1) != 0 ? 0x100 : 0;
    *(_DWORD *)(v309 + 16) = 0;
    v312 = v311 + 1;
    *(_WORD *)(v309 + 20) = v312;
    if ( v310 > 0 )
    {
      do
      {
        v309 += 56;
        if ( (*(_WORD *)(v309 + 20) & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v309);
          v3 = 0;
          v10 = 1;
        }
        --v310;
        *(_WORD *)(v309 + 20) = v312;
        *(_DWORD *)(v309 + 16) = 0;
      }
      while ( v310 > 0 );
      goto LABEL_145;
    }
    goto LABEL_1403;
  }
  if ( (_DWORD)v15 == 74 )
    goto LABEL_565;
  v282 = v15 - 69;
  if ( v282 )
  {
    v283 = v282 - 1;
    if ( v283 )
    {
      v284 = v283 - 1;
      if ( v284 )
      {
        v285 = v284 - 1;
        if ( v285 )
        {
          if ( v285 != 1 )
            goto LABEL_53;
          goto LABEL_1075;
        }
        v286 = out2Prerelease(v4, v6);
LABEL_534:
        *(_QWORD *)v286 = **((_QWORD **)v6 + 2);
        goto LABEL_244;
      }
      v287 = (unsigned int **)out2Prerelease(v4, v6);
      v288 = (unsigned int *)*((int *)v6 + 1);
LABEL_536:
      *v287 = v288;
      goto LABEL_244;
    }
  }
  else if ( ((unsigned __int8)v10 & *(_BYTE *)(56LL * *((int *)v6 + 3) + v7 + 20)) == 0 )
  {
    goto LABEL_53;
  }
  v289 = v4[33];
  if ( v289 && !*((_DWORD *)v6 + 1) )
  {
    v290 = *(_QWORD *)(v289 + 8);
    --*((_DWORD *)v4 + 70);
    v4[33] = v290;
    v291 = v4[7];
    *(_QWORD *)(v2 + 128) += v291;
    *(_QWORD *)(v2 + 120) = v291;
    v292 = sqlite3VdbeFrameRestore();
    v10 = 1;
    if ( *((_DWORD *)v6 + 2) == 4 )
      v292 = *(_DWORD *)(v4[17] + 24LL * v292 + 8) - 1;
    v5 = v4[17];
    v7 = v4[13];
    v834 = v5;
    v835 = v7;
    v6 = (unsigned __int8 *)(v5 + 24LL * v292);
    goto LABEL_61;
  }
  v821 = *((_DWORD *)v6 + 1);
  *((_DWORD *)v4 + 13) = v821;
  *((_BYTE *)v4 + 196) = v6[8];
  if ( v821 )
  {
    if ( *((_WORD *)v6 + 1) )
    {
      sqlite3VdbeError(v4, "%s constraint failed", off_18028D660[*((unsigned __int16 *)v6 + 1)]);
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
      -1431655765 * ((__int64)&v6[-v834] >> 3),
      (const char *)v4[31],
      (const char *)v4[21]);
  }
  v822 = sqlite3VdbeHalt(v4);
  v60 = v839;
  v14 = v822;
  if ( v822 == 5 )
    *((_DWORD *)v4 + 13) = 5;
  else
    v14 = *((_DWORD *)v4 + 13) != 0 ? 1 : 101;
LABEL_1565:
  while ( 1 )
  {
    v825 = v851;
    if ( v852 < v851 )
      break;
    v826 = *(__int64 (__fastcall **)(__int64))(v60 + 528);
    if ( !v826 )
      break;
    v827 = *(_QWORD *)(v60 + 536);
    v851 += *(unsigned int *)(v60 + 544);
    v828 = v826(v827);
    v60 = v839;
    v3 = 0;
    if ( v828 )
    {
LABEL_1535:
      v851 = -1;
      goto LABEL_1536;
    }
  }
  *((_DWORD *)v4 + 57) += v852;
  if ( *((_DWORD *)v4 + 52) )
    sqlite3VdbeLeave(v4, v825, v60);
  return v14;
}

```

## disassembly

```asm
0x1801eee30  mov     rax, rsp
0x1801eee33  push    rbp
0x1801eee34  push    rbx
0x1801eee35  push    rsi
0x1801eee36  push    rdi
0x1801eee37  push    r12
0x1801eee39  push    r13
0x1801eee3b  push    r14
0x1801eee3d  push    r15
0x1801eee3f  lea     rbp, [rax-178h]
0x1801eee46  sub     rsp, 238h
0x1801eee4d  movaps  xmmword ptr [rax-58h], xmm6
0x1801eee51  movaps  xmmword ptr [rax-68h], xmm7
0x1801eee55  mov     rax, cs:__security_cookie
0x1801eee5c  xor     rax, rsp
0x1801eee5f  mov     [rbp+170h+var_70], rax
0x1801eee66  mov     r13, [rcx]
0x1801eee69  xor     r10d, r10d
0x1801eee6c  mov     r15, rcx
0x1801eee6f  mov     r8, [rcx+88h]
0x1801eee76  mov     r14, r8
0x1801eee79  mov     rsi, [rcx+68h]
0x1801eee7d  mov     r9d, r10d
0x1801eee80  mov     [rsp+270h+var_210], rcx
0x1801eee85  mov     dil, [r13+64h]
0x1801eee89  mov     byte ptr [rsp+270h+var_230], dil
0x1801eee8e  mov     [rsp+270h+var_220], r8
0x1801eee93  mov     [rsp+270h+var_1F8], r13
0x1801eee98  mov     [rbp+170h+var_1E4], r10b
0x1801eee9c  mov     [rbp+170h+var_180], r10
0x1801eeea0  mov     [rsp+270h+var_218], rsi
0x1801eeea5  cmp     [rcx+0D0h], r10d
0x1801eeeac  jz      short loc_1801EEEBD
0x1801eeeae  call    sqlite3VdbeEnter
0x1801eeeb3  mov     r9, [rbp+170h+var_180]
0x1801eeeb7  mov     r8, r14
0x1801eeeba  xor     r10d, r10d
0x1801eeebd  cmp     [r13+210h], r10
0x1801eeec4  jz      short loc_1801EEEE2
0x1801eeec6  mov     eax, [r15+0E4h]
0x1801eeecd  xor     edx, edx
0x1801eeecf  mov     ecx, [r13+220h]
0x1801eeed6  div     ecx
0x1801eeed8  sub     ecx, edx
0x1801eeeda  mov     eax, ecx
0x1801eeedc  mov     [rbp+170h+var_188], rax
0x1801eeee0  jmp     short loc_1801EEEEA
0x1801eeee2  mov     [rbp+170h+var_188], 0FFFFFFFFFFFFFFFFh
0x1801eeeea  cmp     dword ptr [r15+34h], 7
0x1801eeeef  mov     r11d, 1
0x1801eeef5  jz      loc_1801F5221
0x1801eeefb  mov     [r15+34h], r10d
0x1801eeeff  mov     [r15+48h], r10
0x1801eef03  mov     eax, [r13+198h]
0x1801eef0a  mov     [r13+298h], r10d
0x1801eef11  test    eax, eax
0x1801eef13  jnz     loc_1801F51D9
0x1801eef19  movsxd  rax, dword ptr [r15+30h]
0x1801eef1d  mov     edx, r10d
0x1801eef20  mov     r12d, r10d
0x1801eef23  mov     dword ptr [rsp+270h+var_228], r10d
0x1801eef28  mov     [rsp+270h+var_22C], edx
0x1801eef2c  xorps   xmm7, xmm7
0x1801eef2f  mov     [rbp+170h+var_1A8], r10d
0x1801eef33  lea     rcx, [rax+rax*2]
0x1801eef37  lea     r14, [r8+rcx*8]
0x1801eef3b  lea     ecx, [r11+3]
0x1801eef3f  movzx   ebx, byte ptr [r14]
0x1801eef43  add     r9, r11
0x1801eef46  mov     [rbp+170h+var_1A0], r14
0x1801eef4a  mov     eax, 5
0x1801eef4f  mov     [rbp+170h+var_180], r9
0x1801eef53  cmp     ebx, 5Ch ; '\'
0x1801eef56  ja      loc_1801F15D8
0x1801eef5c  jz      loc_1801F1589
0x1801eef62  cmp     ebx, 2Dh ; '-'
0x1801eef65  ja      loc_1801F05EE
0x1801eef6b  jz      loc_1801F050D
0x1801eef71  cmp     ebx, 16h
0x1801eef74  ja      loc_1801EFDE2
0x1801eef7a  jz      loc_1801EFBC5
0x1801eef80  cmp     ebx, 0Bh
0x1801eef83  ja      loc_1801EF998
0x1801eef89  jz      loc_1801EF96D
0x1801eef8f  cmp     ebx, eax
0x1801eef91  ja      loc_1801EF75D
0x1801eef97  jz      loc_1801EF71D
0x1801eef9d  test    ebx, ebx
0x1801eef9f  jz      loc_1801EF32F
0x1801eefa5  sub     ebx, 1
0x1801eefa8  jz      loc_1801F4E01
0x1801eefae  sub     ebx, 1
0x1801eefb1  jz      loc_1801EF202
0x1801eefb7  sub     ebx, 1
0x1801eefba  jz      loc_1801EF15A
0x1801eefc0  cmp     ebx, 1
0x1801eefc3  jnz     loc_1801EF148
0x1801eefc9  mov     rdx, r14
0x1801eefcc  mov     rcx, r15
0x1801eefcf  call    out2Prerelease
0x1801eefd4  movsxd  rcx, dword ptr [r14+4]
0x1801eefd8  mov     r15, rax
0x1801eefdb  mov     rax, [r13+20h]
0x1801eefdf  mov     ebx, [r14+0Ch]
0x1801eefe3  shl     rcx, 5
0x1801eefe7  mov     r12, [rcx+rax+8]
0x1801eefec  mov     rcx, r12
0x1801eefef  call    sqlite3BtreePager
0x1801eeff4  mov     rcx, rax
0x1801eeff7  mov     rsi, rax
0x1801eeffa  call    sqlite3PagerGetJournalMode
0x1801eefff  cmp     ebx, 0FFFFFFFFh
0x1801ef002  mov     rcx, rsi
0x1801ef005  mov     edi, eax
0x1801ef007  cmovz   ebx, eax
0x1801ef00a  call    sqlite3PagerOkToChangeJournalMode
0x1801ef00f  test    eax, eax
0x1801ef011  mov     edx, 1
0x1801ef016  mov     rcx, rsi
0x1801ef019  cmovz   ebx, edi
0x1801ef01c  call    sqlite3PagerFilename
0x1801ef021  mov     ecx, 5
0x1801ef026  cmp     ebx, ecx
0x1801ef028  jnz     short loc_1801EF05C
0x1801ef02a  mov     rcx, rax
0x1801ef02d  call    sqlite3Strlen30
0x1801ef032  test    eax, eax
0x1801ef034  jz      short loc_1801EF042
0x1801ef036  mov     rcx, rsi
0x1801ef039  call    sqlite3PagerWalSupported
0x1801ef03e  test    eax, eax
0x1801ef040  jnz     short loc_1801EF057
0x1801ef042  mov     ebx, edi
0x1801ef044  mov     r12d, dword ptr [rsp+270h+var_228]
0x1801ef049  test    r12d, r12d
0x1801ef04c  jz      loc_1801EF0E2
0x1801ef052  jmp     loc_1801EF0E0
0x1801ef057  mov     ecx, 5
0x1801ef05c  cmp     ebx, edi
0x1801ef05e  jz      short loc_1801EF044
0x1801ef060  cmp     edi, ecx
0x1801ef062  jz      short loc_1801EF068
0x1801ef064  cmp     ebx, ecx
0x1801ef066  jnz     short loc_1801EF044
0x1801ef068  cmp     byte ptr [r13+65h], 0
0x1801ef06d  jz      loc_1801F4D20
0x1801ef073  cmp     dword ptr [r13+0DCh], 1
0x1801ef07b  jg      loc_1801F4D20
0x1801ef081  cmp     edi, ecx
0x1801ef083  jnz     short loc_1801EF0A4
0x1801ef085  mov     rdx, r13
0x1801ef088  mov     rcx, rsi
0x1801ef08b  call    sqlite3PagerCloseWal
0x1801ef090  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef094  test    eax, eax
0x1801ef096  jnz     short loc_1801EF0DB
0x1801ef098  mov     edx, ebx
0x1801ef09a  mov     rcx, rsi
0x1801ef09d  call    sqlite3PagerSetJournalMode
0x1801ef0a2  jmp     short loc_1801EF0BB
0x1801ef0a4  cmp     edi, 4
0x1801ef0a7  jnz     short loc_1801EF0B4
0x1801ef0a9  lea     edx, [rdi-2]
0x1801ef0ac  mov     rcx, rsi
0x1801ef0af  call    sqlite3PagerSetJournalMode
0x1801ef0b4  cmp     dword ptr [rsp+270h+var_228], 0
0x1801ef0b9  jnz     short loc_1801EF0DB
0x1801ef0bb  xor     edx, edx
0x1801ef0bd  lea     ecx, [rdx+5]
0x1801ef0c0  cmp     ebx, ecx
0x1801ef0c2  mov     rcx, r12
0x1801ef0c5  setz    dl
0x1801ef0c8  inc     edx
0x1801ef0ca  call    sqlite3BtreeSetVersion
0x1801ef0cf  mov     r12d, eax
0x1801ef0d2  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef0d6  jmp     loc_1801EF049
0x1801ef0db  mov     r12d, dword ptr [rsp+270h+var_228]
0x1801ef0e0  mov     ebx, edi
0x1801ef0e2  mov     edx, ebx
0x1801ef0e4  mov     rcx, rsi
0x1801ef0e7  call    sqlite3PagerSetJournalMode
0x1801ef0ec  mov     ecx, eax
0x1801ef0ee  mov     word ptr [r15+14h], 2202h
0x1801ef0f5  call    sqlite3JournalModename
0x1801ef0fa  mov     rcx, rax
0x1801ef0fd  mov     [r15+8], rax
0x1801ef101  call    sqlite3Strlen30
0x1801ef106  movzx   edi, byte ptr [rsp+270h+var_230]
0x1801ef10b  mov     rcx, r15
0x1801ef10e  mov     edx, edi
0x1801ef110  mov     [r15+10h], eax
0x1801ef114  mov     byte ptr [r15+16h], 1
0x1801ef119  call    sqlite3VdbeChangeEncoding
0x1801ef11e  mov     r15, [rsp+270h+var_210]
0x1801ef123  xor     r10d, r10d
0x1801ef126  test    r12d, r12d
0x1801ef129  jnz     loc_1801F524D
0x1801ef12f  mov     rsi, [rsp+270h+var_218]
0x1801ef134  mov     r8, [rsp+270h+var_220]
0x1801ef139  mov     r11d, 1
0x1801ef13f  mov     edx, [rsp+270h+var_22C]
0x1801ef143  mov     ecx, 4
0x1801ef148  mov     r13, [rsp+270h+var_1F8]
0x1801ef14d  add     r14, 18h
0x1801ef151  mov     r9, [rbp+170h+var_180]
0x1801ef155  jmp     loc_1801EEF3F
0x1801ef15a  mov     r8d, [r14+8]
0x1801ef15e  lea     rax, [rbp+170h+var_7C+4]
0x1801ef165  mov     edx, [r14+4]
0x1801ef169  lea     r9, [rbp+170h+var_7C]
0x1801ef170  mov     rcx, r13
0x1801ef173  mov     [rsp+270h+var_250], rax
0x1801ef178  mov     [rbp+170h+var_80], r10d
0x1801ef17f  mov     [rbp+170h+var_7C], 0FFFFFFFFFFFFFFFFh
0x1801ef18a  call    sqlite3Checkpoint
0x1801ef18f  xor     r10d, r10d
0x1801ef192  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef196  mov     r12d, eax
0x1801ef199  test    eax, eax
0x1801ef19b  jz      short loc_1801EF1BB
0x1801ef19d  lea     ecx, [r10+5]
0x1801ef1a1  cmp     eax, ecx
0x1801ef1a3  jnz     loc_1801F524D
0x1801ef1a9  mov     r12d, r10d
0x1801ef1ac  mov     dword ptr [rsp+270h+var_228], r10d
0x1801ef1b1  mov     [rbp+170h+var_80], 1
0x1801ef1bb  movsxd  rax, dword ptr [r14+0Ch]
0x1801ef1bf  mov     rdi, r10
0x1801ef1c2  imul    rbx, rax, 38h ; '8'
0x1801ef1c6  add     rbx, rsi
0x1801ef1c9  movsxd  rdx, [rbp+rdi*4+170h+var_80]
0x1801ef1d1  mov     rcx, rbx
0x1801ef1d4  call    sqlite3VdbeMemSetInt64
0x1801ef1d9  mov     r11d, 1
0x1801ef1df  add     rbx, 38h ; '8'
0x1801ef1e3  add     rdi, r11
0x1801ef1e6  cmp     rdi, 3
0x1801ef1ea  jnz     short loc_1801EF1C9
0x1801ef1ec  mov     dil, byte ptr [rsp+270h+var_230]
0x1801ef1f1  mov     r8, [rsp+270h+var_220]
0x1801ef1f6  mov     edx, [rsp+270h+var_22C]
0x1801ef1fa  xor     r10d, r10d
0x1801ef1fd  jmp     loc_1801EF143
0x1801ef202  mov     edx, [r14+8]
0x1801ef206  mov     dword ptr [rsp+270h+var_200], r10d
0x1801ef20b  test    edx, edx
0x1801ef20d  jz      short loc_1801EF226
0x1801ef20f  mov     rax, [r13+30h]
0x1801ef213  mov     rcx, 200100000h
0x1801ef21d  test    rcx, rax
0x1801ef220  jnz     loc_1801F4D4B
0x1801ef226  movsxd  rdi, dword ptr [r14+4]
0x1801ef22a  mov     rsi, [r13+20h]
0x1801ef22e  shl     rdi, 5
0x1801ef232  mov     rbx, [rdi+rsi+8]
0x1801ef237  test    rbx, rbx
0x1801ef23a  jz      loc_1801EF2F0
0x1801ef240  lea     r8, [rsp+270h+var_200]
0x1801ef245  mov     rcx, rbx
0x1801ef248  call    sqlite3BtreeBeginTrans
0x1801ef24d  xor     r10d, r10d
0x1801ef250  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef254  mov     r12d, eax
0x1801ef257  test    eax, eax
0x1801ef259  jnz     loc_1801F4D63
0x1801ef25f  test    byte ptr [r15+0C8h], 20h
0x1801ef267  jz      loc_1801EF2F9
0x1801ef26d  cmp     [r14+8], r10d
0x1801ef271  jz      loc_1801EF2F9
0x1801ef277  cmp     [r13+65h], r10b
0x1801ef27b  jz      short loc_1801EF287
0x1801ef27d  cmp     dword ptr [r13+0DCh], 1
0x1801ef285  jle     short loc_1801EF2F9
0x1801ef287  mov     r8d, [r15+40h]
0x1801ef28b  test    r8d, r8d
0x1801ef28e  jnz     short loc_1801EF2A9
0x1801ef290  inc     dword ptr [r13+2F4h]
0x1801ef297  mov     r8d, [r13+2F0h]
0x1801ef29e  add     r8d, [r13+2F4h]
0x1801ef2a5  mov     [r15+40h], r8d
0x1801ef2a9  dec     r8d
0x1801ef2ac  xor     edx, edx
0x1801ef2ae  mov     rcx, r13
0x1801ef2b1  call    sqlite3VtabSavepoint
0x1801ef2b6  xor     r10d, r10d
0x1801ef2b9  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef2bd  mov     r12d, eax
0x1801ef2c0  test    eax, eax
0x1801ef2c2  jnz     short loc_1801EF2DA
0x1801ef2c4  mov     edx, [r15+40h]
0x1801ef2c8  mov     rcx, rbx
0x1801ef2cb  call    sqlite3BtreeBeginStmt
0x1801ef2d0  mov     r12d, eax
0x1801ef2d3  mov     dword ptr [rsp+270h+var_228], eax
0x1801ef2d7  xor     r10d, r10d
0x1801ef2da  mov     rax, [r13+2F8h]
0x1801ef2e1  mov     [r15+58h], rax
0x1801ef2e5  mov     rax, [r13+300h]
0x1801ef2ec  mov     [r15+60h], rax
  ... truncated ...
```
