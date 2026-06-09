# sqlite3VdbeExec

- ea: `0x1800a4310`
- end: `0x1800ad2d4`
- name: `sqlite3VdbeExec`
- size: `36804`
- prototype: ``
- caller_count: `2`
- callee_count: `150`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180029d80`
- `0x18009cf10`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005980`
- `0x180005b30`
- `0x18000a7f0`
- `0x18000a8a0`
- `0x180016970`
- `0x180022d00`
- `0x180024fa0`
- `0x180027090`
- `0x180027110`
- `0x180029fd0`
- `0x18002a570`
- `0x18002aa20`
- `0x18002b260`
- `0x18002b330`
- `0x18002b590`
- `0x18002be70`
- `0x180031eb0`
- `0x1800349e0`
- `0x180035360`
- `0x18003b880`
- `0x18003bc70`
- `0x18003c1a0`
- `0x18003f950`
- `0x180043620`
- `0x1800447e0`
- `0x180045110`
- `0x18004dba0`
- `0x18004dc20`
- `0x18004dc60`
- `0x18004e010`
- `0x18004e190`
- `0x18004e360`
- `0x18004e5c0`
- `0x180051ed0`
- `0x180052510`
- `0x1800525d0`
- `0x1800526f0`
- `0x180052750`
- `0x180052890`
- `0x180053300`
- `0x180058d40`
- `0x180058e50`
- `0x18005e6d0`
- `0x18005ece0`
- `0x180064b60`
- `0x180067660`
- `0x180067750`
- `0x180067e10`

## string_xrefs

- `0x1800ac799`: `cannot open savepoint - SQL statements in progress`
- `0x1800acc1c`: `cannot commit transaction - SQL statements in progress`
- `0x1800accef`: `cannot rollback - no transaction is active`
- `0x1800accf6`: `cannot commit - no transaction is active`
- `0x1800acdf7`: `abort due to ROLLBACK`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1, __int64 a2, __int64 a3)
{
  _UNKNOWN **v4; // r11
  unsigned __int8 *v5; // r10
  unsigned __int64 v6; // r9
  __int64 *v7; // r14
  _QWORD *v8; // r13
  _DWORD *v9; // r15
  unsigned __int8 v10; // si
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // r11
  unsigned __int64 v13; // rdx
  __int64 kk; // rax
  unsigned int updated; // r12d
  __m128i si128; // xmm8
  __int64 v17; // r8
  int v18; // ebx
  __m128i v19; // xmm10
  unsigned __int8 *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // kr00_8
  __int64 v23; // r8
  unsigned __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rdi
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rbx
  int v45; // edi
  __int16 v46; // si
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rdx
  __int64 v51; // rdi
  __int64 v52; // rsi
  __int64 v53; // rdi
  __int16 v54; // ax
  int v55; // ecx
  __m128i *v56; // rbx
  int v57; // esi
  _DWORD *v58; // rdi
  _DWORD *v59; // rbx
  int v60; // esi
  __m128i *v61; // rdi
  __m128i *v62; // rbx
  __m128i *v63; // rdx
  _DWORD *v64; // r8
  _DWORD *v65; // r15
  _DWORD *v66; // rdi
  __int16 v67; // r12
  _DWORD *v68; // rbx
  __int16 v69; // si
  int v70; // eax
  unsigned __int64 v71; // r14
  _DWORD *v72; // rsi
  _DWORD *v73; // rdi
  __int64 v74; // rdx
  __int16 v75; // bx
  _DWORD *v76; // r14
  __int16 v77; // bx
  __int16 v78; // ax
  __int64 v79; // r9
  __int64 v80; // r8
  __int64 v81; // r8
  __int16 v82; // ax
  double v83; // xmm6_8
  __int16 v84; // ax
  __int64 v85; // rbx
  __int64 v86; // rax
  _DWORD *v87; // rdi
  _DWORD *v88; // rdx
  __int16 v89; // cx
  _DWORD *v90; // rsi
  __int64 v91; // rbx
  __int16 v92; // ax
  __int64 v93; // rax
  unsigned __int8 v94; // r8
  __int64 v95; // rdx
  unsigned __int8 v96; // cl
  _QWORD *v97; // rbx
  _DWORD *v98; // rbx
  __int64 v99; // rcx
  _DWORD *v100; // rbx
  _DWORD *v101; // r15
  __int16 v102; // si
  _DWORD *v103; // r14
  __int16 v104; // bx
  char v105; // al
  __int64 v106; // rdx
  BOOL v107; // eax
  unsigned __int8 v108; // cl
  unsigned int v109; // eax
  char v110; // dl
  __int64 v111; // r12
  __int64 v112; // rdi
  unsigned int v113; // r8d
  __int64 v114; // r13
  int v115; // ecx
  int v116; // edx
  int v117; // esi
  _DWORD *v118; // r15
  _DWORD *v119; // r14
  _DWORD *v120; // rcx
  __int16 v121; // ax
  __int64 v122; // rbx
  _DWORD *v123; // rcx
  __int16 v124; // ax
  __int64 v125; // rdx
  __int64 *v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rcx
  unsigned __int64 v129; // rdx
  _DWORD *v130; // rdx
  __int16 v131; // ax
  unsigned __int64 v132; // rbx
  _DWORD *v133; // rdi
  _DWORD *v134; // rbx
  __int64 v135; // rax
  __int64 v136; // r8
  __int64 v137; // r9
  unsigned int v138; // edx
  unsigned __int64 v139; // rax
  int v140; // ecx
  int v141; // ecx
  __int64 v142; // rax
  __int64 v143; // rcx
  __int64 v144; // rdx
  __int64 v145; // rcx
  __int64 v146; // rdx
  _DWORD *v147; // rax
  __int64 v148; // rbx
  unsigned int v149; // r14d
  unsigned int *v150; // r15
  int v151; // eax
  __int64 v152; // rdi
  int v153; // eax
  _QWORD *v154; // rsi
  unsigned __int64 v155; // rdi
  int v156; // edx
  int v157; // ecx
  unsigned __int8 *v158; // rcx
  __int64 v159; // rax
  __int64 v160; // rcx
  int v161; // eax
  unsigned int v162; // eax
  int Varint32; // eax
  __int64 v164; // rdx
  __int64 v165; // r10
  __int64 v166; // r8
  int v167; // ecx
  __int64 v168; // r12
  unsigned __int8 *v169; // rsi
  unsigned __int64 v170; // r13
  unsigned __int64 v171; // r14
  __int64 v172; // rdi
  __int64 v173; // rax
  unsigned __int8 v174; // al
  int v175; // esi
  __m128i *v176; // rcx
  int v177; // eax
  unsigned __int8 *v178; // rdx
  __int64 v179; // rsi
  void *v180; // r14
  __int64 *v181; // rcx
  __int64 v182; // rbx
  __int64 v183; // rdx
  char v184; // al
  int v186; // edi
  __int64 v187; // r14
  __int64 v188; // rsi
  _DWORD *v189; // rbx
  __int16 v190; // ax
  char v191; // cl
  __int16 v192; // ax
  __int16 v193; // cx
  __int16 v194; // dx
  bool v195; // zf
  double v196; // rcx
  __int16 v197; // dx
  __int16 v198; // ax
  _BYTE *v199; // rdi
  _DWORD *v200; // rbx
  __int16 v201; // cx
  __int16 v202; // cx
  __int16 v203; // cx
  double v204; // rdx
  __int16 v205; // cx
  __int64 v206; // rsi
  int v207; // r15d
  __int64 v208; // r13
  _BYTE *v209; // rdi
  unsigned int *v210; // r12
  int v211; // eax
  int *v212; // r14
  unsigned int *v213; // rbx
  __int16 v214; // ax
  int *v215; // rbx
  unsigned int v216; // ecx
  __int64 v217; // r8
  int v218; // edx
  unsigned int v219; // edi
  unsigned int v220; // r14d
  __int64 v221; // rax
  int v222; // ecx
  unsigned __int64 k; // rax
  _DWORD *v224; // rdi
  unsigned __int64 m; // rax
  int v226; // ecx
  unsigned __int64 n; // rax
  __int64 v228; // rdx
  __int64 v229; // rbx
  _BYTE *v230; // r11
  char *v231; // rbx
  _BYTE *v232; // rdi
  int v233; // eax
  unsigned int *v234; // rsi
  unsigned __int64 v235; // rdx
  __int64 v236; // r8
  __int64 v237; // rcx
  int v238; // eax
  __int64 v239; // rbx
  __int64 v240; // rdx
  __int64 v241; // rdi
  unsigned int v242; // eax
  __int64 v243; // r8
  char v244; // cl
  unsigned __int16 v245; // ax
  int v246; // ecx
  __int64 v247; // r9
  unsigned int v248; // edx
  unsigned int v249; // eax
  __int64 v250; // rax
  size_t v251; // rdi
  const char *v252; // rsi
  _QWORD *v253; // rbx
  __int64 v254; // r10
  unsigned int v255; // r13d
  __int64 *v256; // r12
  _BYTE *v257; // r8
  const char *v258; // r9
  __int64 v259; // rdx
  __int64 v260; // rax
  int v261; // r15d
  int v262; // esi
  int v263; // ebx
  int v264; // r14d
  int v265; // ebx
  int v266; // esi
  __int64 i; // rax
  __int64 *v268; // rcx
  __int64 v269; // rdx
  __int64 v270; // r15
  __int64 v271; // r14
  __int64 v272; // rbx
  char v273; // al
  _QWORD *v274; // r8
  __int64 v275; // rcx
  __int64 v276; // rdx
  __int64 *v277; // rdi
  int v278; // r8d
  unsigned int v279; // edi
  __int64 *v280; // rsi
  __int64 v281; // rcx
  __int64 v282; // rdx
  __int64 v283; // rax
  _QWORD *v284; // rdx
  __int64 v285; // rdi
  __int64 v286; // rbx
  _QWORD *ii; // rdi
  __int64 v288; // rbx
  _QWORD *jj; // rbx
  __int64 v290; // rsi
  __int64 v291; // rbx
  __int64 v292; // rcx
  int v293; // r15d
  __int64 v294; // r14
  __int64 v295; // rax
  __int64 v296; // r12
  unsigned __int8 v297; // cl
  int v298; // edi
  unsigned __int8 *v299; // rcx
  unsigned __int8 v300; // al
  __int64 v301; // rbx
  __int64 v302; // r8
  __int64 Cursor; // rax
  unsigned int v304; // eax
  __int64 v305; // rbx
  __int64 v306; // rax
  int v307; // ecx
  __int64 v308; // rax
  __int64 v309; // rdx
  __int64 v310; // rbx
  __int64 v311; // rax
  __int64 v312; // rbx
  __int64 v313; // rcx
  __int64 v314; // rax
  __int64 v315; // rsi
  int v316; // ecx
  __int64 v317; // rax
  bool v318; // zf
  __int64 v319; // rdx
  __int64 v320; // rcx
  __int64 v321; // r14
  BOOL v322; // r12d
  _DWORD *v323; // rbx
  __int16 v324; // r15
  __int16 v325; // ax
  double v326; // rsi
  _BYTE *v327; // rcx
  int v328; // eax
  __int64 *v329; // rbx
  __int64 v330; // rdx
  char v331; // si
  int v332; // ecx
  char v333; // al
  __int64 v334; // rax
  __int64 v335; // rcx
  __int64 v336; // rcx
  __int64 v337; // rsi
  unsigned __int8 *v338; // r12
  int v339; // edi
  __int64 v340; // rbx
  unsigned int v341; // r10d
  int v342; // ecx
  __int64 v343; // rdx
  __int64 v344; // rdx
  int v345; // ebx
  bool v346; // sf
  __int64 v347; // rcx
  unsigned int v348; // eax
  __int16 v349; // r8
  __int64 v350; // rdx
  int v351; // r8d
  __int64 v352; // rdx
  int v353; // ecx
  bool v354; // cc
  __int64 v355; // rdx
  __int64 v356; // rbx
  _DWORD *v357; // rcx
  int *v358; // rsi
  __int64 v359; // rax
  __int64 v360; // rdi
  int v361; // ecx
  unsigned int v362; // edx
  __int64 v363; // rcx
  __int64 v364; // rdi
  __int64 v365; // rbx
  unsigned int v366; // eax
  __int64 v367; // rdx
  __int64 v368; // rax
  __int64 v369; // rdx
  __int64 v370; // rbx
  __int64 v371; // r14
  unsigned int v372; // edi
  __int64 v373; // r14
  __int64 v374; // rsi
  _BYTE *v375; // rcx
  __int64 v376; // rcx
  __int64 *v377; // rdi
  __int64 v378; // rbx
  int v379; // edi
  __int64 v380; // rcx
  __int64 v381; // rdx
  __int64 v382; // rbx
  _QWORD *v383; // rdi
  __int64 v384; // rsi
  __int64 v385; // r9
  __int64 v386; // rdx
  __int64 v387; // rcx
  __int64 v388; // r9
  __int64 v389; // rdx
  __int64 v390; // rax
  int v391; // r15d
  __int64 v392; // rdi
  __int64 v393; // rsi
  __int64 v394; // r14
  __int64 v395; // rbx
  __int64 v396; // rax
  __int64 v397; // r15
  int v398; // ebx
  __int64 v399; // rdx
  __int64 v400; // rdi
  __int64 v401; // rsi
  __int64 v402; // r14
  __int64 v403; // rax
  __int64 v404; // rax
  unsigned int *v405; // r8
  unsigned int *v406; // rdx
  int mm; // edx
  __int64 v408; // rcx
  _DWORD *v409; // rbx
  __int64 v410; // rax
  __int64 v411; // rax
  const void *v412; // rsi
  int *v413; // rdi
  size_t v414; // rdi
  __int64 v415; // rbx
  __int64 v416; // rdi
  __int64 v417; // rdx
  __int64 v418; // rdx
  __int64 v419; // rdi
  __int64 v420; // rax
  __int64 v421; // rbx
  __int64 *v422; // rcx
  __int64 v423; // rbx
  __int64 v424; // rbx
  __int64 v425; // rdx
  __int64 v426; // rbx
  __int64 v427; // rbx
  _BYTE *v428; // rcx
  __int64 v429; // rbx
  unsigned int v430; // eax
  int v431; // edi
  int v432; // ecx
  int v433; // edi
  __int64 v434; // rsi
  __int64 v435; // rbx
  unsigned int v436; // eax
  __int64 v437; // rsi
  __int64 v438; // rdi
  unsigned __int8 *v439; // rdi
  __int64 v440; // rcx
  _QWORD *v441; // rcx
  _QWORD *v442; // rbx
  int v443; // ecx
  __int64 v444; // rcx
  int v445; // eax
  __int64 v446; // rcx
  __int16 v447; // r8
  __int64 v448; // rdx
  unsigned __int8 *v449; // r12
  __int64 v450; // rdi
  _DWORD *v451; // rbx
  __int16 v452; // r8
  __int64 v453; // r9
  __int64 v454; // rdi
  _DWORD *v455; // rbx
  __int64 v456; // rbx
  __int64 v457; // rdi
  __int64 v458; // rdx
  __int64 v459; // rcx
  __int64 v460; // rbx
  __int64 v461; // rdx
  __int64 v462; // rdx
  __int64 v463; // rax
  __int64 v464; // rdx
  __int64 v465; // rax
  _QWORD *v466; // rdx
  __int64 v467; // rcx
  __int64 v468; // rdx
  __int64 v469; // rbx
  unsigned int v470; // r10d
  int v471; // ecx
  __int64 v472; // rdx
  int v473; // ebx
  int v474; // ebx
  __int64 v475; // rdi
  __int64 v476; // rsi
  __int64 v477; // rax
  unsigned int v478; // r14d
  __int64 v479; // rbx
  __int64 v480; // rdx
  __int64 v481; // r10
  int v482; // r11d
  int v483; // r8d
  _QWORD *nn; // rcx
  __int64 v485; // rax
  _QWORD *i1; // rcx
  __int64 v487; // rcx
  __int64 v488; // rcx
  __int64 v489; // rdi
  __int64 v490; // rax
  unsigned int v491; // esi
  __int64 v492; // rcx
  __int64 v493; // rbx
  __int64 v494; // rbx
  __int64 v495; // rbx
  __int64 v496; // r8
  __int64 v497; // rax
  __int64 v498; // rcx
  _QWORD *v499; // rdx
  __int64 v500; // rbx
  __int64 v501; // rcx
  __int64 v502; // rdx
  __int64 v503; // rax
  _QWORD *v504; // rdx
  __int64 v505; // rdi
  _DWORD *v506; // rbx
  __int64 v507; // rdx
  __int64 v508; // r9
  __int64 v509; // rdx
  __int64 v510; // rax
  __int64 v511; // rdi
  _DWORD *v512; // rbx
  _DWORD *v513; // rdi
  __int64 v514; // rbx
  __int16 v515; // ax
  __int64 *v516; // rax
  __int64 v517; // rdi
  __int64 v518; // rax
  _DWORD *v519; // rax
  __int64 v520; // rsi
  int v521; // edi
  _DWORD *v522; // rbx
  __int64 v523; // rsi
  bool v524; // sf
  __int64 *v525; // r12
  _DWORD *v526; // rdi
  int v527; // edx
  int v528; // esi
  int v529; // r15d
  _DWORD *v530; // rax
  _DWORD *v531; // rbx
  _DWORD *v532; // rcx
  _DWORD *v533; // rdx
  __int64 v534; // rcx
  __int64 v535; // rdx
  void *v536; // rcx
  unsigned __int8 *v537; // rcx
  int v538; // eax
  __int64 v539; // rax
  __int64 v540; // r9
  __int64 v541; // rax
  __int64 v542; // rdx
  __int64 v543; // rcx
  __int64 *v544; // rdi
  __int64 *v545; // rbx
  __int64 v546; // rdx
  __int64 v547; // rcx
  __int64 v548; // rdi
  __int64 v549; // rbx
  __int64 v550; // r8
  __int64 v551; // rax
  __int64 v552; // r9
  __int64 v553; // rdx
  __int64 v554; // rcx
  __int64 v555; // rcx
  __int64 v556; // rbx
  unsigned __int64 v557; // rdx
  __int64 v558; // r8
  unsigned __int8 *v559; // rax
  __int64 *v560; // rbx
  unsigned int *v561; // r8
  __int64 v562; // rdx
  __int64 *v563; // r8
  __int64 v564; // rax
  __int64 v565; // rdx
  __int64 v566; // rcx
  const char *v567; // rax
  __int64 v568; // rdx
  __int64 v569; // rax
  _DWORD *v570; // rax
  __int64 v571; // rcx
  __int128 v572; // rdi
  __int64 v573; // rax
  _DWORD *v574; // rbx
  unsigned int v575; // eax
  int v576; // edx
  _DWORD *v577; // rbx
  _QWORD *v578; // rcx
  _QWORD *v579; // rcx
  __int64 v580; // r14
  __int64 v581; // r15
  __int64 v582; // rax
  _QWORD *v583; // rbx
  unsigned int v584; // esi
  unsigned int v585; // edi
  const char *v586; // rcx
  __int64 v587; // rax
  int v588; // eax
  const char *v589; // rcx
  __int64 v590; // rax
  _DWORD *v591; // r9
  __int64 v592; // rsi
  __int64 v593; // rdi
  unsigned int v594; // r14d
  unsigned __int32 v595; // ebx
  unsigned int v596; // r15d
  __int64 v597; // rcx
  __int64 j; // rax
  __int64 v599; // rdx
  int i2; // r8d
  unsigned __int8 v601; // si
  __int64 v602; // rbx
  unsigned __int8 v603; // si
  unsigned int v604; // edi
  __int64 v605; // r14
  int v606; // edx
  __int64 v607; // rbx
  __int64 *v608; // rax
  __int64 v609; // rdi
  __int64 v610; // rcx
  int v611; // edx
  __int64 v612; // rdx
  __int64 v613; // rax
  __int64 Table; // rsi
  const char *v615; // rdi
  __int64 v616; // r8
  __int64 v617; // r9
  _QWORD *v618; // rax
  __int64 i3; // rdx
  __int64 v620; // rdi
  __int64 v621; // rcx
  __int64 v622; // rbx
  __int64 v623; // rcx
  __int64 (__fastcall *v624)(_QWORD); // rax
  __int64 *v625; // rbx
  __int64 v626; // rdi
  __int64 v627; // r9
  __int64 v628; // rcx
  __int64 v629; // rbx
  _QWORD *v630; // rax
  _QWORD *v631; // rdi
  _DWORD *v632; // rdx
  __int64 v633; // rcx
  __int64 v634; // rbx
  __int64 v635; // r10
  __int64 v636; // rdx
  __int64 v637; // r14
  int *v638; // r11
  unsigned int v639; // r15d
  __int64 **v640; // rbx
  int v641; // r9d
  __m128i v642; // xmm4
  __int64 *v643; // rsi
  __int64 v644; // rdi
  signed int v645; // edx
  __int64 v646; // rcx
  __m128i v647; // xmm3
  __m128i v652; // xmm2
  unsigned int v653; // eax
  __int64 v657; // rax
  __int64 v658; // rdi
  __int64 *v659; // rsi
  __int64 v660; // r14
  unsigned __int8 *v661; // rax
  unsigned int v662; // eax
  const char *v663; // rax
  __int16 v664; // cx
  __int64 v665; // rdx
  __int64 v666; // rdi
  __int64 **v667; // rcx
  __int64 *v668; // rbx
  __int64 v669; // rsi
  unsigned __int64 v670; // rdi
  __int64 v671; // rbx
  int v672; // esi
  __int64 v673; // rdi
  __int64 v674; // rax
  _DWORD *v675; // rbx
  __int64 *v676; // rbx
  __int64 v677; // r10
  __int64 v678; // rcx
  char v679; // di
  __int64 v680; // r8
  __int64 v681; // rdx
  _DWORD *v682; // r9
  __int64 v683; // rdx
  __int64 v684; // rax
  __int64 v685; // rsi
  unsigned int v686; // edi
  __int64 v687; // rbx
  unsigned int v688; // ecx
  __int64 v689; // rcx
  __int64 v690; // rdi
  __int64 v691; // r14
  _DWORD *v692; // rbx
  __int64 v693; // rdx
  __int16 v694; // cx
  __int64 v695; // rdx
  const char *v696; // rax
  unsigned __int64 *v697; // rdi
  unsigned __int64 v698; // rbx
  int v699; // esi
  int v700; // r15d
  void (__fastcall *v701)(_QWORD); // rax
  int v702; // eax
  __int64 (*v703)(void); // rax
  __int64 v704; // rbx
  unsigned __int64 v705; // rax
  __int64 v706; // rcx
  unsigned __int64 v707; // rdx
  unsigned __int64 v708; // r8
  __int64 v709; // rbx
  unsigned __int64 v710; // rax
  int v711; // r8d
  char v712; // al
  const char *v713; // r9
  __int64 v714; // rbx
  __int64 v715; // rbx
  int v716; // ecx
  __int64 v717; // rax
  int v718; // ecx
  __int64 v719; // rax
  const char *v720; // rax
  __int64 v721; // rdx
  char *v722; // rax
  int v723; // r9d
  const char *v724; // rax
  const char *v725; // r8
  unsigned __int8 *v726; // r12
  int v727; // ebx
  int v728; // ecx
  char v729; // al
  __int64 v730; // rdx
  const char *v731; // rdx
  const char *v732; // r8
  __int64 (__fastcall *v733)(_QWORD, _QWORD, _QWORD); // rax
  unsigned int (__fastcall *v734)(_QWORD); // rax
  __int64 v736; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v737; // [rsp+48h] [rbp-C0h]
  unsigned __int8 *v738; // [rsp+50h] [rbp-B8h]
  __int64 v739; // [rsp+58h] [rbp-B0h]
  unsigned int v740; // [rsp+58h] [rbp-B0h]
  unsigned __int8 *v741; // [rsp+60h] [rbp-A8h]
  __int64 v742; // [rsp+68h] [rbp-A0h]
  unsigned __int64 v743; // [rsp+70h] [rbp-98h]
  unsigned __int64 v744; // [rsp+78h] [rbp-90h]
  _DWORD *v746; // [rsp+88h] [rbp-80h]
  __int64 v747; // [rsp+90h] [rbp-78h] BYREF
  BOOL v748; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v749; // [rsp+9Ch] [rbp-6Ch] BYREF
  int *v750; // [rsp+A0h] [rbp-68h] BYREF
  int v751; // [rsp+A8h] [rbp-60h]
  int v752; // [rsp+ACh] [rbp-5Ch]
  int v753; // [rsp+B0h] [rbp-58h] BYREF
  int v754; // [rsp+B4h] [rbp-54h] BYREF
  int v755; // [rsp+B8h] [rbp-50h]
  unsigned int *v756; // [rsp+C0h] [rbp-48h]
  __int64 **v757; // [rsp+C8h] [rbp-40h] BYREF
  int v758; // [rsp+D0h] [rbp-38h] BYREF
  int v759; // [rsp+D4h] [rbp-34h] BYREF
  int v760; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v761; // [rsp+E0h] [rbp-28h] BYREF
  __int64 v762; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v763; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v764; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v765; // [rsp+100h] [rbp-8h] BYREF
  __int128 v766; // [rsp+110h] [rbp+8h]
  __int128 v767; // [rsp+120h] [rbp+18h]
  __int64 v768; // [rsp+130h] [rbp+28h]
  _QWORD v769[2]; // [rsp+138h] [rbp+30h] BYREF
  int v770; // [rsp+148h] [rbp+40h]
  unsigned int v771; // [rsp+14Ch] [rbp+44h]
  int v772; // [rsp+150h] [rbp+48h]
  int v773; // [rsp+154h] [rbp+4Ch]
  int v774; // [rsp+158h] [rbp+50h]
  __int64 v775; // [rsp+160h] [rbp+58h] BYREF
  __int128 v776; // [rsp+168h] [rbp+60h]
  _QWORD *v777; // [rsp+178h] [rbp+70h]
  __int128 v778; // [rsp+180h] [rbp+78h]
  __int64 v779; // [rsp+190h] [rbp+88h]
  __int64 v780; // [rsp+198h] [rbp+90h] BYREF
  _DWORD *v781; // [rsp+1A0h] [rbp+98h]
  unsigned __int16 v782; // [rsp+1B4h] [rbp+ACh]
  char v783; // [rsp+1B6h] [rbp+AEh]
  char v784[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  __int64 v785; // [rsp+1C8h] [rbp+C0h]
  unsigned int v786; // [rsp+1D0h] [rbp+C8h]
  __int16 v787; // [rsp+1D4h] [rbp+CCh]
  _QWORD *v788; // [rsp+1D8h] [rbp+D0h]
  int v789; // [rsp+1E0h] [rbp+D8h]
  char v790[8]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v791; // [rsp+200h] [rbp+F8h]
  unsigned int v792; // [rsp+208h] [rbp+100h]
  __int16 v793; // [rsp+20Ch] [rbp+104h]
  _QWORD *v794; // [rsp+210h] [rbp+108h]
  int v795; // [rsp+218h] [rbp+110h]
  __int64 v796; // [rsp+230h] [rbp+128h] BYREF
  __int64 v797; // [rsp+238h] [rbp+130h]
  __int64 v798; // [rsp+240h] [rbp+138h]
  int v799; // [rsp+254h] [rbp+14Ch]
  int v800; // [rsp+258h] [rbp+150h]
  __int128 v801; // [rsp+260h] [rbp+158h] BYREF
  __int128 v802; // [rsp+270h] [rbp+168h]
  __int128 v803; // [rsp+280h] [rbp+178h]
  __int64 v804; // [rsp+290h] [rbp+188h]
  _QWORD v805[3]; // [rsp+298h] [rbp+190h] BYREF
  __int16 v806; // [rsp+2B4h] [rbp+1ACh]
  char v807; // [rsp+2B6h] [rbp+1AEh]
  char v808; // [rsp+2BAh] [rbp+1B2h]
  _OWORD v809[2]; // [rsp+2C0h] [rbp+1B8h] BYREF
  __int128 v810; // [rsp+2E0h] [rbp+1D8h]
  __int64 v811; // [rsp+2F0h] [rbp+1E8h]
  __int128 v812; // [rsp+2F8h] [rbp+1F0h] BYREF
  __int128 v813; // [rsp+308h] [rbp+200h]
  __m128i v814; // [rsp+318h] [rbp+210h]
  __int64 v815; // [rsp+328h] [rbp+220h]
  _QWORD v816[3]; // [rsp+330h] [rbp+228h] BYREF
  __int16 v817; // [rsp+34Ch] [rbp+244h]
  char v818; // [rsp+34Eh] [rbp+246h]
  _QWORD v819[3]; // [rsp+358h] [rbp+250h] BYREF
  __int16 v820; // [rsp+374h] [rbp+26Ch]
  char v821; // [rsp+376h] [rbp+26Eh]
  _QWORD v822[3]; // [rsp+380h] [rbp+278h] BYREF
  __int16 v823; // [rsp+39Ch] [rbp+294h]
  char v824; // [rsp+39Eh] [rbp+296h]
  _QWORD v825[4]; // [rsp+3A8h] [rbp+2A0h] BYREF
  __int16 v826; // [rsp+3C8h] [rbp+2C0h]
  int v827; // [rsp+3D8h] [rbp+2D0h]
  int v828; // [rsp+3DCh] [rbp+2D4h] BYREF
  int v829; // [rsp+3E0h] [rbp+2D8h] BYREF
  _UNKNOWN *retaddr; // [rsp+490h] [rbp+388h] BYREF

  v4 = &retaddr;
  v5 = (unsigned __int8 *)a1[17];
  v6 = 0;
  v7 = a1;
  v8 = (_QWORD *)*a1;
  LOBYTE(v4) = 0;
  v9 = (_DWORD *)a1[13];
  v10 = *(_BYTE *)(*a1 + 100);
  v737 = v10;
  v741 = v5;
  v738 = v5;
  v742 = *a1;
  v755 = (int)v4;
  v744 = 0;
  v746 = v9;
  if ( *((_DWORD *)a1 + 52) )
  {
    sqlite3VdbeEnter(a1, a2, a3, 0);
    v6 = 0;
    v5 = v741;
  }
  if ( v8[66] )
    v11 = (unsigned int)(*((_DWORD *)v8 + 136) - *((_DWORD *)v7 + 57) % *((_DWORD *)v8 + 136));
  else
    v11 = -1;
  v12 = 0x180000000uLL;
  v13 = 1;
  v743 = v11;
  if ( *((_DWORD *)v7 + 13) == 7 )
  {
    v154 = v8;
    goto LABEL_582;
  }
  *((_DWORD *)v7 + 13) = 0;
  v7[9] = 0;
  *((_DWORD *)v8 + 166) = 0;
  if ( *((_DWORD *)v8 + 102) )
  {
LABEL_2030:
    v154 = (_QWORD *)v742;
    updated = 9;
    goto LABEL_489;
  }
  kk = *((int *)v7 + 12);
  updated = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v17 = 0;
  v18 = 0;
  v19 = _mm_load_si128((const __m128i *)&_xmm);
  v20 = &v5[24 * kk];
  v739 = 0;
  v751 = 0;
LABEL_9:
  while ( 2 )
  {
    v21 = *v20;
    ++v6;
    v738 = v20;
    v744 = v6;
    v22 = kk;
    kk = v21;
    switch ( *v20 )
    {
      case 0u:
        LODWORD(v251) = *((_DWORD *)v20 + 1);
        v252 = (const char *)*((_QWORD *)v20 + 2);
        LODWORD(v747) = v251;
        if ( !(_DWORD)v251 )
        {
          if ( *((int *)v8 + 56) > 0 )
          {
            sqlite3VdbeError(v7, "cannot open savepoint - SQL statements in progress");
            updated = 5;
            goto LABEL_487;
          }
          if ( v252 )
            v251 = strlen_0(v252) & 0x3FFFFFFF;
          LODWORD(v739) = sqlite3VtabSavepoint(v8, 0, (unsigned int)(*((_DWORD *)v8 + 188) + *((_DWORD *)v8 + 189)));
          updated = v739;
          if ( (_DWORD)v739 )
            goto LABEL_487;
          kk = sqlite3DbMallocRawNN(v8, (unsigned int)v251 + 33LL);
          v253 = (_QWORD *)kk;
          if ( kk )
          {
            *(_QWORD *)kk = kk + 32;
            memcpy_0((void *)(kk + 32), v252, (unsigned int)(v251 + 1));
            if ( *((_BYTE *)v8 + 101) == (_BYTE)v739 )
            {
              ++*((_DWORD *)v8 + 188);
            }
            else
            {
              *((_BYTE *)v8 + 101) = v739;
              *((_BYTE *)v8 + 109) = 1;
            }
            v253[3] = v8[92];
            v8[92] = v253;
            v253[1] = v8[95];
            kk = v8[96];
            v253[2] = kk;
          }
          goto LABEL_845;
        }
        v254 = v742;
        v255 = 0;
        v256 = *(__int64 **)(v742 + 736);
        if ( !v256 )
        {
LABEL_1963:
          sqlite3VdbeError(v7, "no such savepoint: %s", v252);
LABEL_1964:
          v154 = (_QWORD *)v742;
          updated = 1;
          goto LABEL_488;
        }
        while ( 2 )
        {
          v257 = (_BYTE *)*v256;
          v258 = v252;
LABEL_784:
          v259 = (unsigned __int8)*v257;
          v260 = *(unsigned __int8 *)v258;
          if ( (_DWORD)v259 == (_DWORD)v260 )
          {
            if ( !*v257 )
            {
              if ( *(int *)(v742 + 224) > 0 && (_DWORD)v251 == 1 )
              {
                sqlite3VdbeError(v7, "cannot release savepoint - SQL statements in progress");
                updated = 5;
                goto LABEL_487;
              }
              if ( v256[3] || !*(_BYTE *)(v742 + 109) )
              {
                v261 = 0;
              }
              else
              {
                v261 = 1;
                if ( (_DWORD)v251 == 1 )
                {
                  v154 = (_QWORD *)v742;
                  v740 = sqlite3VdbeCheckFk(v7, 1);
                  if ( v740 )
                  {
                    updated = v740;
                  }
                  else
                  {
                    *(_BYTE *)(v742 + 101) = 1;
                    if ( (unsigned int)sqlite3VdbeHalt(v7) != 5 )
                    {
                      LODWORD(v739) = *((_DWORD *)v7 + 13);
                      if ( !(_DWORD)v739 )
                      {
                        v254 = v742;
                        *(_BYTE *)(v742 + 109) = 0;
                        goto LABEL_816;
                      }
                      updated = *((_DWORD *)v7 + 13);
                      *(_BYTE *)(v742 + 101) = 0;
LABEL_488:
                      v11 = v743;
LABEL_489:
                      v155 = v744;
                      goto LABEL_490;
                    }
                    updated = 5;
                    *((_DWORD *)v7 + 12) = (v738 - v741) / 24;
                    *(_BYTE *)(v742 + 101) = 0;
                    *((_DWORD *)v7 + 13) = 5;
                  }
LABEL_2066:
                  v11 = v743;
                  v155 = v744;
                  goto LABEL_2067;
                }
              }
              v262 = *(_DWORD *)(v742 + 752);
              if ( (_DWORD)v251 == 2 )
              {
                v263 = 0;
                v264 = *(_DWORD *)(v742 + 44) & 1;
                if ( *(int *)(v742 + 40) > 0 )
                {
                  do
                  {
                    LODWORD(v739) = sqlite3BtreeTripAllCursors(
                                      *(_QWORD *)(32LL * v263 + *(_QWORD *)(v254 + 32) + 8),
                                      516,
                                      v264 ^ 1u);
                    if ( (_DWORD)v739 )
                      goto LABEL_992;
                    v254 = v742;
                    ++v263;
                  }
                  while ( v263 < *(_DWORD *)(v742 + 40) );
                  LODWORD(v251) = v747;
                }
              }
              else
              {
                v264 = 0;
              }
              v265 = 0;
              v255 = v262 + ~v255;
              if ( *(int *)(v254 + 40) > 0 )
              {
                while ( 1 )
                {
                  LODWORD(v739) = sqlite3BtreeSavepoint(
                                    *(_QWORD *)(32LL * v265 + *(_QWORD *)(v254 + 32) + 8),
                                    (unsigned int)v251,
                                    v255);
                  v266 = v739;
                  if ( (_DWORD)v739 )
                    break;
                  v254 = v742;
                  if ( ++v265 >= *(_DWORD *)(v742 + 40) )
                    goto LABEL_811;
                }
LABEL_992:
                updated = v739;
LABEL_486:
                v7 = a1;
LABEL_487:
                v154 = (_QWORD *)v742;
                goto LABEL_488;
              }
              v266 = v739;
LABEL_811:
              if ( v264 )
              {
                for ( i = *(_QWORD *)(v254 + 8); i; i = *(_QWORD *)(i + 16) )
                {
                  *(_DWORD *)(i + 200) &= ~2u;
                  *(_DWORD *)(i + 200) |= 1u;
                }
                sqlite3ResetAllSchemasOfConnection(v254);
                v254 = v742;
                *(_DWORD *)(v742 + 44) |= 1u;
              }
              v7 = a1;
              if ( v266 )
              {
                updated = v739;
                goto LABEL_487;
              }
LABEL_816:
              v268 = *(__int64 **)(v254 + 736);
              if ( v268 != v256 )
              {
                while ( 2 )
                {
                  *(_QWORD *)(v254 + 736) = v268[3];
                  if ( (unsigned __int64)v268 >= *(_QWORD *)(v254 + 496) )
                    goto LABEL_2077;
                  if ( (unsigned __int64)v268 >= *(_QWORD *)(v254 + 480) )
                  {
                    *v268 = *(_QWORD *)(v254 + 472);
                    *(_QWORD *)(v254 + 472) = v268;
                    goto LABEL_826;
                  }
                  if ( (unsigned __int64)v268 < *(_QWORD *)(v254 + 488) )
                  {
LABEL_2077:
                    if ( *(_QWORD *)(v254 + 776) )
                      measureAllocationSize(v254, v268);
                    else
                      sqlite3_free(v268);
                    v254 = v742;
                  }
                  else
                  {
                    *v268 = *(_QWORD *)(v254 + 456);
                    *(_QWORD *)(v254 + 456) = v268;
                  }
LABEL_826:
                  --*(_DWORD *)(v254 + 752);
                  v268 = *(__int64 **)(v254 + 736);
                  if ( v268 == v256 )
                    break;
                  continue;
                }
              }
              if ( (_DWORD)v251 == 1 )
              {
                *(_QWORD *)(v254 + 736) = v256[3];
                if ( (unsigned __int64)v256 >= *(_QWORD *)(v254 + 496) )
                  goto LABEL_2078;
                if ( (unsigned __int64)v256 >= *(_QWORD *)(v254 + 480) )
                {
                  kk = *(_QWORD *)(v254 + 472);
                  *v256 = kk;
                  *(_QWORD *)(v254 + 472) = v256;
                  goto LABEL_837;
                }
                if ( (unsigned __int64)v256 < *(_QWORD *)(v254 + 488) )
                {
LABEL_2078:
                  if ( *(_QWORD *)(v254 + 776) )
                    kk = measureAllocationSize(v254, v256);
                  else
                    kk = sqlite3_free(v256);
                  v254 = v742;
                }
                else
                {
                  kk = *(_QWORD *)(v254 + 456);
                  *v256 = kk;
                  *(_QWORD *)(v254 + 456) = v256;
                }
LABEL_837:
                if ( !v261 )
                {
                  --*(_DWORD *)(v254 + 752);
LABEL_841:
                  kk = sqlite3VtabSavepoint(v254, (unsigned int)v251, v255);
                  LODWORD(v739) = kk;
                  updated = kk;
                  if ( (_DWORD)kk )
                    goto LABEL_487;
LABEL_844:
                  v9 = v746;
LABEL_845:
                  if ( *((_BYTE *)v7 + 199) == 3 )
                  {
                    updated = 101;
LABEL_847:
                    v154 = (_QWORD *)v742;
                    goto LABEL_2066;
                  }
                  goto LABEL_569;
                }
              }
              else
              {
                *(_QWORD *)(v254 + 760) = v256[1];
                kk = v256[2];
                *(_QWORD *)(v254 + 768) = kk;
                if ( !v261 || (_DWORD)v251 == 2 )
                  goto LABEL_841;
              }
              updated = v739;
              goto LABEL_844;
            }
          }
          else if ( *(unsigned __int8 *)(v259 + v12 + 1132160) != *(unsigned __int8 *)(v260 + v12 + 1132160) )
          {
            v256 = (__int64 *)v256[3];
            if ( !v256 )
              goto LABEL_1963;
            ++v255;
            continue;
          }
          break;
        }
        ++v257;
        ++v258;
        goto LABEL_784;
      case 1u:
        v726 = v20;
        v727 = *((_DWORD *)v20 + 1);
        v728 = *((_DWORD *)v20 + 2);
        if ( v727 != *((unsigned __int8 *)v8 + 101) )
        {
          if ( v728 )
          {
            sqlite3RollbackAll(v8, 516);
            v729 = 1;
          }
          else
          {
            if ( v727 && *((int *)v8 + 56) > 0 )
            {
              sqlite3VdbeError(v7, "cannot commit transaction - SQL statements in progress");
              updated = 5;
              goto LABEL_487;
            }
            updated = sqlite3VdbeCheckFk(v7, 1);
            if ( updated )
              goto LABEL_847;
            v726 = v738;
            v729 = v727;
          }
          *((_BYTE *)v8 + 101) = v729;
          if ( (unsigned int)sqlite3VdbeHalt(v7) == 5 )
          {
            v154 = (_QWORD *)v742;
            v730 = (unsigned __int128)((v726 - v741) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64;
            updated = 5;
            *((_DWORD *)v7 + 12) = ((unsigned __int64)v730 >> 63) + (v730 >> 2);
            *((_BYTE *)v8 + 101) = 1 - v727;
            *((_DWORD *)v7 + 13) = 5;
          }
          else
          {
            sqlite3CloseSavepoints(v8);
            updated = 101;
            v154 = (_QWORD *)v742;
            if ( *((_DWORD *)v7 + 13) )
              updated = 1;
          }
          goto LABEL_2066;
        }
        if ( v727 )
        {
          v731 = "cannot commit - no transaction is active";
          if ( v728 )
            v731 = "cannot rollback - no transaction is active";
          sqlite3VdbeError(v7, v731);
        }
        else
        {
          sqlite3VdbeError(v7, "cannot start a transaction within a transaction");
        }
        goto LABEL_1964;
      case 2u:
        v753 = 0;
        v269 = *((unsigned int *)v20 + 2);
        if ( (_DWORD)v269 )
        {
          kk = v8[6];
          if ( (kk & 0x200100000LL) != 0 )
          {
            updated = 8;
            if ( (kk & 0x100000) == 0 )
              updated = 11;
            goto LABEL_1967;
          }
        }
        v270 = v8[4];
        v271 = 32LL * *((int *)v20 + 1);
        v272 = *(_QWORD *)(v271 + v270 + 8);
        if ( !v272 )
          goto LABEL_884;
        if ( *(_BYTE *)(v272 + 17) || (v273 = *(_BYTE *)(v272 + 16)) == 0 || v273 == 1 && (_DWORD)v269 )
        {
          kk = btreeBeginTrans(*(_QWORD *)(v271 + v270 + 8), v269, &v753);
        }
        else
        {
          v274 = *(_QWORD **)(v272 + 8);
          kk = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v274[3] + 80LL) + 40LL));
          v753 = kk;
          if ( !(_DWORD)v269 )
          {
            updated = 0;
            LODWORD(v739) = 0;
LABEL_865:
            v277 = a1;
            v20 = v738;
            if ( (a1[25] & 0x20) != 0 && *((_DWORD *)v738 + 2) && (!*((_BYTE *)v8 + 101) || *((int *)v8 + 55) > 1) )
            {
              v278 = *((_DWORD *)a1 + 16);
              if ( !v278 )
              {
                v278 = ++*((_DWORD *)v8 + 189) + *((_DWORD *)v8 + 188);
                *((_DWORD *)a1 + 16) = v278;
              }
              LODWORD(v739) = sqlite3VtabSavepoint(v8, 0, (unsigned int)(v278 - 1));
              updated = v739;
              if ( !(_DWORD)v739 )
              {
                v279 = *((_DWORD *)a1 + 16);
                v280 = *(__int64 **)(v272 + 8);
                if ( *(_BYTE *)(v272 + 17) )
                {
                  ++*(_DWORD *)(v272 + 20);
                  if ( !*(_BYTE *)(v272 + 18) )
                    btreeLockCarefully(v272);
                }
                v281 = *v280;
                if ( (signed int)v279 > *(_DWORD *)(*v280 + 128) && *(_BYTE *)(v281 + 10) )
                {
                  updated = pagerOpenSavepoint(v281, v279);
                  LODWORD(v739) = updated;
                }
                else
                {
                  updated = 0;
                  LODWORD(v739) = 0;
                }
                if ( *(_BYTE *)(v272 + 17) )
                {
                  v195 = (*(_DWORD *)(v272 + 20))-- == 1;
                  if ( v195 )
                    unlockBtreeMutex(v272);
                }
                v277 = a1;
                v10 = v737;
              }
              v12 = 0x180000000uLL;
              v5 = v741;
              v277[11] = v8[95];
              kk = v8[96];
              v277[12] = kk;
LABEL_884:
              if ( updated )
                goto LABEL_486;
              v20 = v738;
            }
            if ( *((_WORD *)v20 + 1) )
            {
              if ( v753 != *((_DWORD *)v20 + 3)
                || (kk = *((unsigned int *)v738 + 4), *(_DWORD *)(*(_QWORD *)(v271 + v270 + 24) + 4LL) != (_DWORD)kk) )
              {
                v7 = a1;
                v721 = a1[21];
                if ( v721 )
                  sqlite3DbFreeNN(v8, v721);
                v722 = (char *)sqlite3DbMallocRawNN(v8, 28);
                if ( v722 )
                  strcpy(v722, "database schema has changed");
                a1[21] = (__int64)v722;
                if ( **(_DWORD **)(32LL * *((int *)v738 + 1) + v8[4] + 24) != v753 )
                  sqlite3ResetOneSchema(v8);
                updated = 17;
                *((_DWORD *)a1 + 50) = a1[25] & 0xFFFFFFEC | 1;
                goto LABEL_487;
              }
              v20 = v738;
            }
            v7 = a1;
            v9 = v746;
            goto LABEL_573;
          }
          kk = *(_QWORD *)v272;
          v275 = *v274;
          v276 = *(unsigned int *)(*(_QWORD *)v272 + 752LL);
          if ( (int)v276 <= *(_DWORD *)(*v274 + 128LL) || !*(_BYTE *)(v275 + 10) )
          {
            updated = 0;
            LODWORD(v739) = 0;
            goto LABEL_863;
          }
          kk = pagerOpenSavepoint(v275, v276);
        }
        LODWORD(v739) = kk;
        updated = kk;
LABEL_863:
        if ( !updated )
        {
          v5 = v741;
          v12 = 0x180000000uLL;
          goto LABEL_865;
        }
        v7 = a1;
        v154 = (_QWORD *)v742;
        v11 = v743;
        v155 = v744;
        if ( (_BYTE)updated != 5 )
          goto LABEL_490;
        *((_DWORD *)a1 + 12) = (v738 - v741) / 24;
        *((_DWORD *)a1 + 13) = updated;
LABEL_2067:
        while ( 2 )
        {
          if ( v155 >= v11 )
          {
            v734 = (unsigned int (__fastcall *)(_QWORD))v154[66];
            if ( v734 )
            {
              v11 += *((unsigned int *)v154 + 136);
              if ( !v734(v154[67]) )
                continue;
              v11 = -1;
              updated = 9;
LABEL_490:
              if ( *((_BYTE *)v154 + 103) )
              {
                updated = 7;
              }
              else if ( updated == 8458 )
              {
                sqlite3_log(
                  11,
                  "%s at line %d of [%.10s]",
                  "database corruption",
                  100680,
                  "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
                updated = 11;
              }
              if ( v7[21] || updated == 3082 )
              {
                *((_DWORD *)v7 + 13) = updated;
                if ( updated == 3082 )
                {
LABEL_2056:
                  sqlite3_log(
                    updated,
                    "statement aborts at %d: [%s] %s",
                    (v738 - v741) / 24,
                    (const char *)v7[31],
                    (const char *)v7[21]);
                  if ( *((_BYTE *)v7 + 199) == 2 )
                    sqlite3VdbeHalt(v7);
                  if ( updated == 3082 )
                  {
                    sqlite3OomFault(v154);
                  }
                  else if ( updated == 11 && !*((_BYTE *)v154 + 101) )
                  {
                    v154[6] |= 0x200000000uLL;
                  }
                  updated = 1;
                  if ( (_BYTE)v755 )
                    sqlite3ResetOneSchema(v154);
                  continue;
                }
              }
              else
              {
                switch ( updated )
                {
                  case 0x64u:
                    v732 = "another row available";
                    break;
                  case 0x65u:
                    v732 = "no more rows available";
                    break;
                  case 0x204u:
                    v732 = "abort due to ROLLBACK";
                    break;
                  default:
                    v732 = "unknown error";
                    if ( (unsigned __int8)updated < 0x1Du && off_180113F00[(unsigned __int8)updated] )
                      v732 = off_180113F00[(unsigned __int8)updated];
                    break;
                }
                sqlite3VdbeError(v7, "%s", v732);
                *((_DWORD *)v7 + 13) = updated;
              }
              if ( (((unsigned __int8)updated - 10) & 0xFFFFFFFB) == 0 )
              {
                v733 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*v154 + 128LL);
                if ( v733 )
                  LODWORD(v733) = v733(*v154, 0, 0);
                *((_DWORD *)v154 + 23) = (_DWORD)v733;
              }
              goto LABEL_2056;
            }
          }
          break;
        }
        *((_DWORD *)v7 + 57) += v155;
        if ( *((_DWORD *)v7 + 52) )
          vdbeLeave(v7);
        return updated;
      case 3u:
        v827 = 0;
        v829 = -1;
        v828 = -1;
        v575 = sqlite3Checkpoint(
                 (_DWORD)v8,
                 *((_DWORD *)v20 + 1),
                 *((_DWORD *)v20 + 2),
                 (unsigned int)&v828,
                 (__int64)&v829);
        LODWORD(v739) = v575;
        updated = v575;
        if ( v575 )
        {
          if ( v575 != 5 )
            goto LABEL_487;
          updated = 0;
          v576 = 1;
          LODWORD(v739) = 0;
        }
        else
        {
          v576 = v827;
        }
        v577 = &v9[14 * *((int *)v738 + 3)];
        if ( (v577[5] & 0x9000) != 0 )
        {
          vdbeReleaseAndSetInt64(&v9[14 * *((int *)v738 + 3)], v576);
        }
        else
        {
          *(_QWORD *)v577 = v576;
          *((_WORD *)v577 + 10) = 4;
        }
        v578 = v577 + 14;
        if ( (v577[19] & 0x9000) != 0 )
        {
          vdbeReleaseAndSetInt64(v578, v828);
        }
        else
        {
          *v578 = v828;
          *((_WORD *)v577 + 38) = 4;
        }
        v579 = v577 + 28;
        kk = v829;
        if ( (v577[33] & 0x9000) != 0 )
        {
          kk = vdbeReleaseAndSetInt64(v579, v829);
          v20 = v738;
        }
        else
        {
          *v579 = v829;
          v20 = v738;
          *((_WORD *)v577 + 66) = 4;
        }
        goto LABEL_571;
      case 4u:
        v580 = 56LL * *((int *)v20 + 2) + v7[13];
        if ( (*(_WORD *)(v580 + 20) & 0x9000) != 0 )
          v580 = out2PrereleaseWithClear(v580, 1);
        else
          *(_WORD *)(v580 + 20) = 4;
        v581 = *(_QWORD *)(32LL * *((int *)v738 + 1) + v8[4] + 8);
        v582 = *(_QWORD *)(v581 + 8);
        v583 = *(_QWORD **)v582;
        v584 = *(unsigned __int8 *)(*(_QWORD *)v582 + 9LL);
        v585 = v584;
        if ( *((_DWORD *)v738 + 3) != -1 )
          v585 = *((_DWORD *)v738 + 3);
        if ( *((_BYTE *)v583 + 21) >= 3u || *(_QWORD *)v583[10] && (__int64)v583[12] > 0 )
          v585 = *(unsigned __int8 *)(*(_QWORD *)v582 + 9LL);
        if ( *((_BYTE *)v583 + 19) || (char *)*v583 == byte_18013D380 )
          v586 = byte_180114B34;
        else
          v586 = (const char *)v583[27];
        if ( v585 == 5 )
        {
          if ( !v586
            || (strlen_0(v586) & 0x3FFFFFFF) == 0
            || *((_BYTE *)v583 + 17)
            || !*((_BYTE *)v583 + 8) && ((v587 = v583[9], **(int **)v587 < 2) || !*(_QWORD *)(*(_QWORD *)v587 + 104LL)) )
          {
            v585 = v584;
            goto LABEL_1658;
          }
        }
        if ( v585 == v584 || v584 != 5 && v585 != 5 )
          goto LABEL_1658;
        if ( !*((_BYTE *)v8 + 101) || *((int *)v8 + 55) > 1 )
        {
          v7 = a1;
          v725 = "out of";
          if ( v585 == 5 )
            v725 = "into";
          updated = 1;
          sqlite3VdbeError(a1, "cannot change %s wal mode from within a transaction", v725);
          v154 = (_QWORD *)v742;
          goto LABEL_488;
        }
        if ( v584 != 5 )
        {
          if ( v584 == 4 )
            sqlite3PagerSetJournalMode(v583, 2);
          if ( updated )
            goto LABEL_1659;
LABEL_1657:
          updated = sqlite3BtreeSetVersion(v581, (unsigned int)(v585 == 5) + 1);
          LODWORD(v739) = updated;
LABEL_1658:
          if ( !updated )
            goto LABEL_1660;
LABEL_1659:
          v585 = v584;
LABEL_1660:
          v588 = sqlite3PagerSetJournalMode(v583, v585);
          *(_WORD *)(v580 + 20) = 8706;
          if ( v588 == 6 )
          {
            *(_QWORD *)(v580 + 8) = 0;
            kk = 0;
          }
          else
          {
            v589 = off_18010F1B8[v588];
            *(_QWORD *)(v580 + 8) = v589;
            if ( v589 )
              kk = strlen_0(v589) & 0x3FFFFFFF;
            else
              kk = 0;
          }
          v10 = v737;
          *(_DWORD *)(v580 + 16) = kk;
          *(_BYTE *)(v580 + 22) = 1;
          if ( v737 != 1 )
            kk = sqlite3VdbeMemTranslate(v580, v737);
          v7 = a1;
          if ( updated )
            goto LABEL_487;
          v20 = v738;
          v9 = v746;
          goto LABEL_571;
        }
        updated = 0;
        if ( !v583[37] )
        {
          v754 = 0;
          updated = pagerLockDb(v583, 1);
          if ( updated )
            goto LABEL_1651;
          updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*v583 + 56LL))(*v583, v583[38], 0, &v754);
          if ( updated )
            goto LABEL_1651;
          if ( v754 )
          {
            updated = pagerOpenWal(v583);
            if ( updated )
              goto LABEL_1651;
          }
        }
        if ( !v583[37] )
          goto LABEL_1651;
        updated = pagerExclusiveLock(v583);
        if ( updated )
          goto LABEL_1651;
        LODWORD(v739) = sqlite3WalClose(
                          v583[37],
                          (_DWORD)v8,
                          *((unsigned __int8 *)v583 + 15),
                          *((_DWORD *)v583 + 50),
                          v583[35]);
        updated = v739;
        v583[37] = 0;
        pagerFixMaplimit(v583);
        if ( (_DWORD)v739 )
        {
          if ( !*((_BYTE *)v583 + 8) )
          {
            pagerUnlockDb(v583, 1);
            goto LABEL_1659;
          }
LABEL_1651:
          if ( updated )
          {
            LODWORD(v739) = updated;
            goto LABEL_1659;
          }
        }
        sqlite3PagerSetJournalMode(v583, v585);
        goto LABEL_1657;
      case 5u:
        v590 = *((int *)v20 + 2);
        if ( (_DWORD)v590 )
          v591 = &v9[14 * v590];
        else
          v591 = 0;
        kk = sqlite3RunVacuum(v7 + 21, v8, *((unsigned int *)v20 + 1), v591);
        goto LABEL_959;
      case 6u:
        v635 = a1[14];
        v636 = 14LL * *((int *)v20 + 3);
        v637 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v638 = &v9[v636 + 14];
        v639 = v9[v636];
        v640 = *(__int64 ***)(v637 + 48);
        v641 = *v638;
        v642 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v638, (__m128i)(unsigned __int64)v638);
        v643 = *v640;
        v644 = **v640;
        if ( *v638 > 0 )
        {
          v645 = 0;
          if ( (unsigned int)v641 < 8 || _isa_available < 6 )
            goto LABEL_2079;
          do
          {
            v646 = v645;
            v647 = _mm_move_epi64(v19);
            _XMM0 = _mm_cvtepi32_epi64(
                      _mm_add_epi32(
                        _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v645), 0), v647),
                        _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            _XMM0 = _mm_cvtepi32_epi64(
                      _mm_add_epi32(
                        _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v645 + 2), 0), v647),
                        _mm_move_epi64(si128)));
            *(__m128i *)(v635 + 8LL * v645) = _mm_add_epi64(_XMM1, v642);
            __asm { vpmullq xmm1, xmm0, xmm7 }
            v652 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v645 + 4), 0);
            v653 = v645 + 6;
            *(__m128i *)(v635 + 8LL * v645 + 16) = _mm_add_epi64(_XMM1, v642);
            v645 += 8;
            _XMM0 = _mm_cvtepi32_epi64(_mm_add_epi32(_mm_add_epi32(v652, v647), _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            *(__m128i *)(v635 + 8 * v646 + 32) = _mm_add_epi64(_XMM1, v642);
            _XMM0 = _mm_cvtepi32_epi64(
                      _mm_add_epi32(
                        _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v653), 0), v647),
                        _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            *(__m128i *)(v635 + 8 * v646 + 48) = _mm_add_epi64(_XMM1, v642);
          }
          while ( v645 < v641 - (v641 & 7) );
          if ( v645 < v641 )
          {
LABEL_2079:
            do
            {
              v657 = v645++;
              *(_QWORD *)(v635 + 8 * v657) = &v638[14 * v645];
            }
            while ( v645 < v641 );
          }
        }
        HIDWORD(v736) = HIDWORD(v635);
        LODWORD(v739) = (*(__int64 (__fastcall **)(__int64 **, _QWORD, _QWORD))(v644 + 64))(
                          v640,
                          v639,
                          *((_QWORD *)v738 + 2));
        updated = v739;
        sqlite3VtabImportErrmsg(a1, v643);
        if ( (_DWORD)v739 )
        {
          v7 = a1;
          goto LABEL_487;
        }
        kk = (*(__int64 (__fastcall **)(__int64 **))(v644 + 80))(v640);
        v20 = v738;
        v13 = 1;
        v5 = v741;
        *(_BYTE *)(v637 + 2) = 0;
        if ( (_DWORD)kk )
          goto LABEL_1260;
        v9 = v746;
        v7 = a1;
        v10 = v737;
        goto LABEL_108;
      case 7u:
        v763 = 0;
        if ( *((_BYTE *)v8 + 103) )
          goto LABEL_1991;
        kk = *((_QWORD *)v20 + 2);
        v676 = *(__int64 **)(kk + 16);
        if ( !v676 )
          goto LABEL_2001;
        v677 = *v676;
        if ( !*v676 )
          goto LABEL_2001;
        if ( !*(_QWORD *)(v677 + 104) )
        {
          v5 = v741;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
          continue;
        }
        v678 = 0;
        v679 = *((_BYTE *)v8 + 108);
        v680 = v7[14];
        v681 = *((unsigned int *)v738 + 2);
        v682 = &v9[14 * *((int *)v738 + 3)];
        if ( (int)v681 > 0 )
        {
          do
          {
            *(_QWORD *)(v680 + 8 * v678) = v682;
            v682 += 14;
            v678 = (unsigned int)(v678 + 1);
          }
          while ( (int)v678 < (int)v681 );
        }
        *((_BYTE *)v8 + 108) = v738[2];
        LODWORD(v739) = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v677 + 104))(
                          v676,
                          v681,
                          v680,
                          &v763);
        *((_BYTE *)v8 + 108) = v679;
        updated = v739;
        kk = sqlite3VtabImportErrmsg(v7, v676);
        if ( (_DWORD)v739 )
        {
          if ( (_BYTE)v739 == 19 )
          {
            kk = *((_QWORD *)v738 + 2);
            if ( *(_BYTE *)(kk + 28) )
            {
              kk = *((unsigned __int16 *)v738 + 1);
              if ( (_WORD)kk != 4 )
              {
                if ( (_WORD)kk == 5 )
                  LOBYTE(kk) = 2;
                *((_BYTE *)v7 + 196) = kk;
                goto LABEL_487;
              }
              v20 = v738;
              updated = 0;
              LODWORD(v739) = 0;
              goto LABEL_571;
            }
          }
          v20 = v738;
        }
        else
        {
          v20 = v738;
          if ( *((_DWORD *)v738 + 1) )
          {
            kk = v763;
            v8[7] = v763;
          }
        }
        ++v7[7];
        if ( (_DWORD)v739 )
          goto LABEL_487;
        goto LABEL_571;
      case 8u:
      case 0xB5u:
        v712 = *((_BYTE *)v8 + 110);
        if ( (v712 & 0x41) != 0 && *((_BYTE *)v7 + 197) != 0xFE )
        {
          v713 = (const char *)*((_QWORD *)v20 + 2);
          if ( v713 || (v713 = (const char *)v7[31]) != 0 )
          {
            if ( (v712 & 0x40) != 0 )
            {
              v714 = sqlite3VdbeExpandSql(v7, v713);
              ((void (__fastcall *)(_QWORD, __int64))v8[31])(v8[32], v714);
              sqlite3_free(v714);
            }
            else if ( *((int *)v8 + 57) <= 1 )
            {
              ((void (__fastcall *)(__int64, _QWORD, __int64 *))v8[31])(1, v8[32], v7);
            }
            else
            {
              v715 = sqlite3MPrintf(v8, "-- %s", v713);
              ((void (__fastcall *)(__int64, _QWORD, __int64 *, __int64))v8[31])(1, v8[32], v7, v715);
              if ( v715 )
                sqlite3DbFreeNN(v8, v715);
            }
            v5 = v741;
            v12 = 0x180000000uLL;
            v17 = HIDWORD(v739);
            v13 = 1;
          }
        }
        kk = *((unsigned int *)v738 + 1);
        if ( (int)kk < dword_18013C358 )
          goto LABEL_1940;
        v20 = v738;
        if ( *v738 == 0xB5 )
          goto LABEL_575;
        v716 = 1;
        if ( *((int *)v7 + 36) > 1 )
        {
          do
          {
            v717 = v7[17];
            if ( *(_BYTE *)(v717 + 24LL * v716) == 15 )
              *(_DWORD *)(v717 + 24LL * v716 + 4) = 0;
            ++v716;
          }
          while ( v716 < *((_DWORD *)v7 + 36) );
          v13 = 1;
        }
        LODWORD(kk) = 0;
LABEL_1940:
        v20 = v738;
        *((_DWORD *)v738 + 1) = kk + 1;
        ++*((_DWORD *)v7 + 59);
        goto LABEL_1260;
      case 9u:
        goto LABEL_1825;
      case 0xAu:
        v23 = 14LL * *((int *)v20 + 1);
        LOWORD(v9[v23 + 5]) = 4;
        v24 = (__int64)((unsigned __int128)((v20 - v5) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 2;
        *(_QWORD *)&v9[v23] = (int)(v24 + (v24 >> 63));
        goto LABEL_1825;
      case 0xBu:
        v25 = 14LL * *((int *)v20 + 1);
        kk = *((_DWORD *)v738 + 3) - 1;
        *(_QWORD *)&v9[v25] = kk;
        LOWORD(v9[v25 + 5]) = 4;
        v20 = v738;
        if ( *((_DWORD *)v738 + 2) )
          goto LABEL_1260;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v18 = v751;
        continue;
      case 0xCu:
        v27 = 14LL * *((int *)v20 + 1);
        LOWORD(v9[v27 + 5]) = 4;
        v28 = (__int64)((unsigned __int128)((v20 - v5) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 2;
        kk = (int)(v28 + (v28 >> 63));
        v20 = &v5[24 * v9[v27]];
        *(_QWORD *)&v9[v27] = kk;
        goto LABEL_573;
      case 0xDu:
        v98 = &v9[14 * *((int *)v20 + 1)];
        kk = *((unsigned __int16 *)v98 + 10);
        if ( (kk & 4) != 0 )
          goto LABEL_304;
        if ( (kk & 0x28) != 0 )
        {
          sqlite3VdbeIntegerAffinity(&v9[14 * *((int *)v20 + 1)], 1);
        }
        else
        {
          if ( (kk & 2) == 0 )
            goto LABEL_300;
          applyNumericAffinity(&v9[14 * *((int *)v20 + 1)], 1);
          v5 = v741;
          v12 = 0x180000000uLL;
        }
        kk = *((unsigned __int16 *)v98 + 10);
LABEL_300:
        if ( (kk & 4) != 0 )
        {
          v17 = HIDWORD(v739);
          v13 = 1;
LABEL_304:
          LOWORD(kk) = kk & 0xF240 | 4;
          *((_WORD *)v98 + 10) = kk;
          v8 = (_QWORD *)v742;
          v20 = v738 + 24;
          v6 = v744;
          v18 = v751;
          continue;
        }
        v20 = v738;
        if ( !*((_DWORD *)v738 + 2) )
        {
          updated = 20;
          goto LABEL_487;
        }
        goto LABEL_1259;
      case 0xEu:
        if ( (int)v17 >= 0 )
        {
          if ( (_DWORD)v17 )
            kk = *((_DWORD *)v20 + 3) - 1;
          else
            kk = *((_DWORD *)v20 + 2) - 1;
          v8 = (_QWORD *)v742;
          v20 = &v5[24 * kk + 24];
          v18 = v751;
        }
        else
        {
          kk = *((_DWORD *)v20 + 1) - 1;
          v8 = (_QWORD *)v742;
          v20 = &v5[24 * kk + 24];
          v18 = v751;
        }
        continue;
      case 0xFu:
        v136 = v7[33];
        if ( v136 )
        {
          v137 = *(_QWORD *)(v136 + 40);
          v138 = (((int)v20 - *((_DWORD *)v7 + 34)) / 24) & 7;
          v139 = (unsigned __int64)(unsigned int)(((int)v20 - *((_DWORD *)v7 + 34)) / 24) >> 3;
          v140 = *(unsigned __int8 *)(v139 + v137);
          if ( _bittest(&v140, v138) )
            goto LABEL_1258;
          v141 = v140 | (1 << v138);
          v13 = 1;
          *(_BYTE *)(v139 + v137) = v141;
        }
        else if ( *(_DWORD *)(v7[17] + 4) == *((_DWORD *)v20 + 1) )
        {
          goto LABEL_473;
        }
        v17 = HIDWORD(v739);
        kk = (__int64)v738;
        *((_DWORD *)v738 + 1) = *(_DWORD *)(v7[17] + 4);
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x10u:
        kk = sqlite3VdbeBooleanValue(&v9[14 * *((int *)v20 + 1)], *((unsigned int *)v20 + 3));
        if ( (_DWORD)kk )
          goto LABEL_442;
        v20 = v738;
        goto LABEL_571;
      case 0x11u:
        kk = sqlite3VdbeBooleanValue(&v9[14 * *((int *)v20 + 1)], *((_DWORD *)v20 + 3) == 0);
        if ( !(_DWORD)kk )
          goto LABEL_442;
        goto LABEL_894;
      case 0x12u:
        v142 = *((int *)v20 + 1);
        if ( (int)v142 < 0 )
        {
          LOBYTE(v20) = *(_BYTE *)((v9[14 * *((int *)v20 + 3) + 5] & 0x3F) + v12 + 1105952);
          goto LABEL_455;
        }
        v143 = *(_QWORD *)(v7[15] + 8 * v142);
        v144 = *((int *)v738 + 3);
        if ( (int)v144 >= *(unsigned __int16 *)(v143 + 74) )
        {
          v13 = 1;
          LODWORD(v20) = *((_DWORD *)v738 + 4);
LABEL_455:
          kk = 1;
          LOWORD(kk) = 1 << ((_BYTE)v20 - 1);
          goto LABEL_456;
        }
        v145 = *(unsigned int *)(v143 + 4 * v144 + 120);
        v13 = 1;
        if ( (unsigned int)v145 < 0xC )
        {
          kk = *(unsigned __int8 *)(v145 + v12 + 1111560);
        }
        else
        {
          kk = 4;
          if ( (v145 & 1) == 0 )
            LOWORD(kk) = 8;
        }
LABEL_456:
        v20 = v738;
        if ( ((unsigned __int16)kk & *((_WORD *)v738 + 1)) != 0 )
          goto LABEL_1260;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v18 = v751;
        continue;
      case 0x13u:
        v130 = &v9[14 * *((int *)v20 + 1)];
        v131 = *((_WORD *)v130 + 10);
        v132 = (unsigned __int64)&v9[14 * *((int *)v20 + 2)];
        if ( (v131 & 1) == 0 )
        {
          if ( (v131 & 0x24) != 0 )
          {
            kk = *(_QWORD *)v130 == 0;
LABEL_422:
            if ( (*(_WORD *)(v132 + 20) & 0x9000) != 0 )
            {
              kk = vdbeReleaseAndSetInt64(v132, kk);
              v20 = v738;
              goto LABEL_571;
            }
            v20 = v738;
            *(_QWORD *)v132 = kk;
            *(_WORD *)(v132 + 20) = 4;
            goto LABEL_574;
          }
          if ( (v131 & 8) != 0 )
          {
            _XMM0.m128i_i64[0] = *(_QWORD *)v130;
LABEL_419:
            if ( *(double *)_XMM0.m128i_i64 != 0.0 )
            {
              kk = 0;
              goto LABEL_422;
            }
          }
          else if ( (v131 & 0x12) != 0 )
          {
            memRealValue(&v9[14 * *((int *)v20 + 1)]);
            v17 = HIDWORD(v739);
            v12 = 0x180000000uLL;
            v5 = v741;
            goto LABEL_419;
          }
          kk = 1;
          goto LABEL_422;
        }
        kk = 36864;
        if ( (*(_WORD *)(v132 + 20) & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v20 + 2)], v130);
          v20 = v738;
          goto LABEL_571;
        }
        v13 = 1;
LABEL_428:
        *(_WORD *)(v132 + 20) = 1;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x14u:
        kk = v7[15];
        v146 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        if ( !v146 || !*(_BYTE *)(v146 + 2) )
          goto LABEL_16;
        v147 = &v9[14 * *((int *)v20 + 3)];
        if ( (v147[5] & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v20 + 3)], v146);
          goto LABEL_1257;
        }
        v13 = 1;
        *((_WORD *)v147 + 10) = 1;
        goto LABEL_473;
      case 0x15u:
      case 0x16u:
      case 0x17u:
      case 0x18u:
        v321 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        *(_BYTE *)(v321 + 2) = 0;
        *(_BYTE *)(v321 + 3) = 0;
        *(_DWORD *)(v321 + 32) = 0;
        if ( *(_BYTE *)(v321 + 4) )
        {
          v322 = 0;
          v323 = &v9[14 * *((int *)v20 + 3)];
          v324 = *((_WORD *)v323 + 10);
          if ( (v324 & 0x2E) == 2 )
            applyNumericAffinity(v323, 0);
          v325 = *((_WORD *)v323 + 10);
          if ( (v325 & 0x24) != 0 )
          {
            v326 = *(double *)v323;
          }
          else if ( (v325 & 8) != 0 )
          {
            _XMM0.m128i_i64[0] = *(_QWORD *)v323;
            if ( *(double *)v323 >= -9.223372036854775e18 )
            {
              if ( *(double *)_XMM0.m128i_i64 <= 9.223372036854775e18 )
                *(_QWORD *)&v326 = (unsigned int)(int)*(double *)_XMM0.m128i_i64;
              else
                v326 = NAN;
            }
            else
            {
              v326 = -0.0;
            }
          }
          else if ( (v325 & 0x12) != 0 && *((_QWORD *)v323 + 1) )
          {
            v326 = COERCE_DOUBLE(memIntValue(v323, v13));
          }
          else
          {
            v326 = 0.0;
          }
          kk = *((unsigned __int16 *)v323 + 10);
          *((_WORD *)v323 + 10) = v324;
          if ( (kk & 0x24) == 0 )
          {
            if ( (kk & 8) == 0 )
            {
              if ( (kk & 1) != 0 || (unsigned int)v21 >= 0x17 )
              {
LABEL_1022:
                updated = v739;
                goto LABEL_1257;
              }
              v327 = *(_BYTE **)(v321 + 48);
              if ( *v327 || (v327[1] & 8) == 0 )
              {
                kk = btreeLast(v327, &v748);
                LODWORD(v739) = kk;
                if ( (_DWORD)kk )
                  goto LABEL_992;
              }
              else
              {
                v748 = 0;
                LODWORD(v739) = 0;
              }
              goto LABEL_1021;
            }
            v328 = sqlite3IntFloatCompare(*(_QWORD *)&v326, v13);
            if ( v328 <= 0 )
            {
              if ( v328 < 0 && (v21 & 1) != 0 )
                LODWORD(v21) = v21 + 1;
            }
            else if ( (v21 & 1) == 0 )
            {
              LODWORD(v21) = v21 - 1;
            }
          }
          v329 = (__int64 *)(v321 + 48);
          LODWORD(v739) = sqlite3BtreeTableMoveto(*(_QWORD *)(v321 + 48), *(_QWORD *)&v326, 0, &v748);
          *(double *)(v321 + 80) = v326;
          if ( (_DWORD)v739 )
            goto LABEL_992;
        }
        else
        {
          v329 = (__int64 *)(v321 + 48);
          v331 = *(_BYTE *)(*(_QWORD *)(v321 + 48) + 3LL) & 2;
          v322 = v331 != 0;
          v332 = *((_DWORD *)v20 + 4);
          v805[0] = *(_QWORD *)(v321 + 56);
          v806 = v332;
          v333 = 1;
          if ( (((_BYTE)v21 - 1) & 1) != 0 )
            v333 = -1;
          v807 = v333;
          v334 = *((int *)v738 + 3);
          v808 = 0;
          v805[1] = &v9[14 * v334];
          kk = sqlite3BtreeIndexMoveto(*v329, v805, &v748);
          LODWORD(v739) = kk;
          if ( (_DWORD)kk )
            goto LABEL_992;
          if ( v331 && !v808 )
            goto LABEL_1021;
        }
        kk = v748;
        if ( (int)v21 >= 23 )
        {
          if ( v748 >= 0 && (v748 || (_DWORD)v21 != 24) )
          {
            v748 = 0;
            goto LABEL_1011;
          }
          v335 = *v329;
          v748 = 0;
          kk = sqlite3BtreeNext(v335, 0);
LABEL_1014:
          LODWORD(v739) = kk;
          if ( (_DWORD)kk )
          {
            updated = kk;
            if ( (_DWORD)kk != 101 )
              goto LABEL_486;
            v20 = v738;
            v13 = 1;
            v5 = v741;
            updated = 0;
            v748 = 1;
            LODWORD(v739) = 0;
            goto LABEL_1260;
          }
          goto LABEL_1011;
        }
        if ( v748 > 0 || !v748 && (_DWORD)v21 == 21 )
        {
          v336 = *v329;
          v748 = 0;
          *(_BYTE *)(v336 + 1) &= 0xF1u;
          *(_WORD *)(v336 + 70) = 0;
          if ( !*(_BYTE *)v336 )
          {
            v330 = *(unsigned __int16 *)(v336 + 86);
            if ( (_WORD)v330 )
            {
              kk = *(_QWORD *)(v336 + 136);
              if ( *(_BYTE *)(kk + 8) )
              {
                *(_WORD *)(v336 + 86) = v330 - 1;
                LODWORD(v739) = 0;
                goto LABEL_1011;
              }
            }
          }
          kk = btreePrevious(v336, v330);
          goto LABEL_1014;
        }
        kk = *v329;
        v748 = *(_BYTE *)*v329 != 0;
LABEL_1021:
        if ( v748 )
          goto LABEL_1022;
LABEL_1011:
        v7 = a1;
        v12 = 0x180000000uLL;
        v9 = v746;
        v195 = !v322;
        updated = v739;
        v13 = 1;
        v10 = v737;
        v17 = HIDWORD(v739);
        v5 = v741;
        if ( v195 )
        {
LABEL_70:
          v8 = (_QWORD *)v742;
          v20 = v738 + 24;
          v6 = v744;
          v18 = v751;
        }
        else
        {
          v8 = (_QWORD *)v742;
          v20 = v738 + 48;
          v6 = v744;
          v18 = v751;
        }
        continue;
      case 0x19u:
        kk = v7[15];
        v355 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        if ( !v355 || *(_BYTE *)(v355 + 2) )
          goto LABEL_1825;
        goto LABEL_16;
      case 0x1Au:
        kk = *(unsigned __int16 *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 12LL);
        if ( (int)kk < *((_DWORD *)v20 + 4) )
          goto LABEL_1066;
        goto LABEL_575;
      case 0x1Bu:
      case 0x1Cu:
      case 0x1Du:
LABEL_1066:
        v356 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v357 = &v9[14 * *((int *)v20 + 3)];
        v781 = &v9[14 * *((int *)v738 + 3)];
        v782 = *((_WORD *)v738 + 8);
        if ( v782 )
        {
          v358 = (int *)(v356 + 36);
          v780 = *(_QWORD *)(v356 + 56);
          v783 = 0;
          updated = sqlite3BtreeIndexMoveto(*(_QWORD *)(v356 + 48), &v780, v356 + 36);
          LODWORD(v739) = updated;
        }
        else
        {
          if ( (v357[5] & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v357, 1) )
            goto LABEL_1991;
          v359 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v356 + 56));
          v360 = v359;
          if ( !v359 )
            goto LABEL_1991;
          sqlite3VdbeRecordUnpack(*(_QWORD *)(v356 + 56), (unsigned int)v781[4], *((_QWORD *)v781 + 1), v359);
          *(_BYTE *)(v360 + 30) = 0;
          v358 = (int *)(v356 + 36);
          LODWORD(v739) = sqlite3BtreeIndexMoveto(*(_QWORD *)(v356 + 48), v360, v356 + 36);
          updated = v739;
          sqlite3DbFreeNN(v8, v360);
        }
        if ( updated )
          goto LABEL_487;
        v361 = *v358;
        *(_BYTE *)(v356 + 2) = *v358 != 0;
        *(_BYTE *)(v356 + 3) = 0;
        *(_DWORD *)(v356 + 32) = 0;
        kk = *v738;
        if ( (_BYTE)kk == 29 )
        {
          if ( v361 )
          {
LABEL_569:
            v20 = v738;
LABEL_570:
            v10 = v737;
            goto LABEL_571;
          }
        }
        else if ( !v361 )
        {
          if ( (_BYTE)kk != 27 )
          {
            v20 = v738;
            v10 = v737;
            if ( *v738 == 26 )
            {
              kk = *((unsigned __int16 *)v738 + 8);
              *(_WORD *)(v356 + 12) = kk;
            }
            goto LABEL_571;
          }
          v362 = 0;
          if ( !v782 )
            goto LABEL_569;
          while ( 1 )
          {
            kk = v362;
            if ( (v781[14 * v362 + 5] & 1) != 0 )
              break;
            if ( (int)++v362 >= v782 )
              goto LABEL_569;
          }
        }
LABEL_442:
        v20 = v738;
LABEL_443:
        v5 = v741;
        goto LABEL_1259;
      case 0x1Eu:
        v363 = 14LL * *((int *)v20 + 3);
        if ( (v9[v363 + 5] & 0x24) != 0 )
          goto LABEL_1093;
        v812 = *(_OWORD *)&v9[v363];
        v813 = *(_OWORD *)&v9[v363 + 4];
        _XMM0 = *(__m128i *)&v9[v363 + 8];
        v814 = _XMM0;
        v815 = *(_QWORD *)&v9[v363 + 12];
        if ( (BYTE4(v813) & 4) != 0 )
          goto LABEL_1091;
        if ( (BYTE4(v813) & 0x28) != 0 )
        {
          sqlite3VdbeIntegerAffinity(&v812, 1);
        }
        else
        {
          if ( (BYTE4(v813) & 2) == 0 )
            goto LABEL_1091;
          applyNumericAffinity(&v812, 1);
          v5 = v741;
        }
        v13 = 1;
LABEL_1091:
        if ( (BYTE4(v813) & 4) == 0 )
        {
LABEL_473:
          v20 = v738;
          goto LABEL_1260;
        }
        v364 = v812;
LABEL_1094:
        LODWORD(v750) = 0;
        v365 = *(_QWORD *)(v7[15] + 8LL * *((int *)v738 + 1));
        v366 = sqlite3BtreeTableMoveto(*(_QWORD *)(v365 + 48), v364, 0, &v750);
        *(_QWORD *)(v365 + 80) = v364;
        updated = v366;
        *(_BYTE *)(v365 + 2) = 0;
        *(_DWORD *)(v365 + 32) = 0;
        LODWORD(v739) = v366;
        kk = (unsigned int)v750;
        *(_BYTE *)(v365 + 3) = 0;
        *(_DWORD *)(v365 + 36) = kk;
        if ( !(_DWORD)kk )
        {
          if ( updated )
            goto LABEL_487;
          v20 = v738;
          goto LABEL_571;
        }
        v20 = v738;
        if ( *((_DWORD *)v738 + 2) )
        {
          v5 = v741;
          goto LABEL_1259;
        }
        v723 = 97204;
        goto LABEL_1980;
      case 0x1Fu:
LABEL_1093:
        v364 = *(_QWORD *)&v9[14 * *((int *)v738 + 3)];
        goto LABEL_1094;
      case 0x20u:
      case 0x89u:
        v427 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        kk = 0;
        LODWORD(v750) = 0;
        v428 = *(_BYTE **)(v427 + 48);
        if ( (_BYTE)v21 == 0x89 )
        {
          *(_DWORD *)(v427 + 36) = -1;
          if ( !*v428 )
            goto LABEL_1226;
        }
        else if ( !*v428 && (v428[1] & 8) != 0 )
        {
          *(_BYTE *)(v427 + 2) = 0;
          updated = 0;
          *(_BYTE *)(v427 + 3) = 0;
          *(_DWORD *)(v427 + 32) = 0;
          LODWORD(v739) = 0;
          goto LABEL_1237;
        }
        updated = btreeLast(v428, &v750);
        LODWORD(v739) = updated;
        kk = (unsigned int)v750;
        *(_WORD *)(v427 + 2) = (unsigned __int8)v750;
        *(_DWORD *)(v427 + 32) = 0;
        if ( updated )
          goto LABEL_487;
        v17 = HIDWORD(v739);
        v12 = 0x180000000uLL;
        v5 = v741;
        v13 = 1;
LABEL_1237:
        v20 = v738;
        if ( *((int *)v738 + 2) <= 0 )
          goto LABEL_571;
        if ( (_DWORD)kk )
          goto LABEL_443;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x21u:
        v429 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 48LL);
        v430 = moveToRoot(v429, 1);
        updated = v430;
        if ( v430 )
        {
          if ( v430 == 16 )
          {
            v20 = v738;
            v13 = 1;
            v5 = v741;
            updated = 0;
            v752 = 1;
            LODWORD(v739) = 0;
            goto LABEL_1260;
          }
          v431 = v752;
        }
        else
        {
          v431 = 0;
          updated = moveToLeftmost(v429);
        }
        if ( updated )
          goto LABEL_487;
        LODWORD(v739) = 0;
        if ( v431 )
        {
          v752 = v431;
          goto LABEL_1256;
        }
        kk = sqlite3BtreeRowCountEst(v429);
        if ( kk >= 0 )
        {
          v432 = (__int16)sqlite3LogEst(kk);
          kk = (__int64)v738;
          if ( v432 < *((_DWORD *)v738 + 3) )
          {
            v5 = v741;
            v13 = 1;
            v752 = 1;
            v20 = v738;
            goto LABEL_1260;
          }
        }
        v20 = v738;
        v752 = 0;
        LODWORD(v739) = 0;
        goto LABEL_571;
      case 0x22u:
      case 0x23u:
        ++*((_DWORD *)v7 + 55);
        goto LABEL_1262;
      case 0x24u:
LABEL_1262:
        v433 = 1;
        kk = v7[15];
        v434 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        v435 = *(_QWORD *)(v434 + 48);
        if ( *(_BYTE *)v434 == 1 )
        {
          if ( *(_BYTE *)(v435 + 88) )
          {
            v436 = vdbeSorterFlushPMA(*(_QWORD *)(v434 + 48), 1);
            kk = vdbeSorterJoinAll(v435, v436);
            LODWORD(v739) = kk;
            if ( !(_DWORD)kk )
            {
              kk = vdbeSorterSetupMerge(v435);
              LODWORD(v739) = kk;
              v433 = 0;
            }
          }
          else if ( *(_QWORD *)(v435 + 56) )
          {
            v433 = 0;
            kk = vdbeSorterSort(v435 + 96, v435 + 56);
            LODWORD(v739) = kk;
          }
          else
          {
            v433 = 1;
            LODWORD(v739) = 0;
          }
        }
        else
        {
          kk = moveToRoot(*(_QWORD *)(v434 + 48), 1);
          LODWORD(v739) = kk;
          if ( (_DWORD)kk )
          {
            if ( (_DWORD)kk == 16 )
            {
              v433 = 1;
              LODWORD(v739) = 0;
            }
          }
          else
          {
            v433 = 0;
            kk = moveToLeftmost(v435);
            LODWORD(v739) = kk;
          }
          *(_BYTE *)(v434 + 3) = 0;
          *(_DWORD *)(v434 + 32) = 0;
        }
        updated = v739;
        if ( (_DWORD)v739 )
          goto LABEL_487;
        v20 = v738;
        *(_BYTE *)(v434 + 2) = v433;
        if ( *((int *)v738 + 2) <= 0 || !v433 )
          goto LABEL_570;
        v5 = v741;
        goto LABEL_1259;
      case 0x25u:
        v437 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v438 = *(_QWORD *)(v437 + 48);
        if ( *(_BYTE *)(v438 + 88) )
        {
          if ( *(_BYTE *)(v438 + 89) )
          {
            LODWORD(v739) = vdbePmaReaderNext(*(_QWORD *)(v438 + 16), 1);
            if ( !(_DWORD)v739 && !*(_QWORD *)(*(_QWORD *)(v438 + 16) + 24LL) )
            {
              v439 = v738;
              LODWORD(v739) = 101;
              goto LABEL_1313;
            }
          }
          else
          {
            v440 = *(_QWORD *)(v438 + 24);
            LODWORD(v750) = 0;
            LODWORD(v739) = vdbeMergeEngineStep(v440, &v750);
            if ( !(_DWORD)v739 && (_DWORD)v750 )
            {
              v439 = v738;
              LODWORD(v739) = 101;
              goto LABEL_1313;
            }
          }
LABEL_1299:
          v439 = v738;
LABEL_1313:
          updated = v739;
          *(_DWORD *)(v437 + 32) = 0;
          if ( (_DWORD)v739 )
          {
            if ( (_DWORD)v739 != 101 )
              goto LABEL_487;
            updated = 0;
            *(_BYTE *)(v437 + 2) = 1;
            LODWORD(v739) = 0;
          }
          else
          {
            *(_BYTE *)(v437 + 2) = 0;
            ++*((_DWORD *)v7 + *((unsigned __int16 *)v439 + 1) + 53);
LABEL_1825:
            v738 = &v741[24 * *((_DWORD *)v738 + 2) - 24];
          }
          goto LABEL_1826;
        }
        v441 = *(_QWORD **)(v438 + 56);
        *(_QWORD *)(v438 + 56) = v441[1];
        v441[1] = 0;
        if ( *(_QWORD *)(v438 + 64) )
        {
LABEL_1296:
          v443 = 101;
          if ( *(_QWORD *)(v438 + 56) )
            v443 = 0;
          LODWORD(v739) = v443;
          goto LABEL_1299;
        }
        while ( 1 )
        {
          v442 = (_QWORD *)v441[1];
          if ( (unsigned __int64)v441 >= v8[62] )
            break;
          if ( (unsigned __int64)v441 < v8[60] )
          {
            if ( (unsigned __int64)v441 < v8[61] )
              break;
            *v441 = v8[57];
            v8[57] = v441;
          }
          else
          {
            *v441 = v8[59];
            v8[59] = v441;
          }
LABEL_1295:
          v441 = v442;
          if ( !v442 )
            goto LABEL_1296;
        }
        if ( v8[97] )
          measureAllocationSize(v8, v441);
        else
          sqlite3_free(v441);
        goto LABEL_1295;
      case 0x26u:
        v439 = v20;
        v437 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v444 = *(_QWORD *)(v437 + 48);
        *(_BYTE *)(v444 + 1) &= 0xF1u;
        *(_WORD *)(v444 + 70) = 0;
        if ( !*(_BYTE *)v444 )
        {
          v13 = *(unsigned __int16 *)(v444 + 86);
          if ( (_WORD)v13 )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v444 + 136) + 8LL) )
            {
              *(_WORD *)(v444 + 86) = v13 - 1;
              LODWORD(v739) = 0;
              goto LABEL_1313;
            }
          }
        }
        v445 = btreePrevious(v444, v13);
        goto LABEL_1312;
      case 0x27u:
        v439 = v20;
        v437 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v446 = *(_QWORD *)(v437 + 48);
        *(_WORD *)(v446 + 70) = 0;
        *(_BYTE *)(v446 + 1) &= 0xF9u;
        if ( *(_BYTE *)v446 )
        {
          v445 = btreeNext(v446, 1);
        }
        else
        {
          v447 = *(_WORD *)(v446 + 86);
          v448 = *(_QWORD *)(v446 + 136);
          *(_WORD *)(v446 + 86) = v447 + 1;
          if ( (unsigned __int16)(v447 + 1) < *(_WORD *)(v448 + 24) )
          {
            if ( *(_BYTE *)(v448 + 8) )
            {
              LODWORD(v739) = 0;
              goto LABEL_1313;
            }
            v445 = moveToLeftmost(v446);
          }
          else
          {
            *(_WORD *)(v446 + 86) = v447;
            v445 = btreeNext(v446, v448);
          }
        }
LABEL_1312:
        LODWORD(v739) = v445;
        goto LABEL_1313;
      case 0x28u:
      case 0x29u:
      case 0x2Au:
      case 0x2Du:
        v468 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v469 = *(_QWORD *)(v468 + 48);
        v819[0] = *(_QWORD *)(v468 + 56);
        v820 = *((_WORD *)v20 + 8);
        v821 = -((unsigned __int8)v21 < 0x2Au);
        v819[1] = &v9[14 * *((int *)v20 + 3)];
        getCellInfo(v469);
        v470 = *(_DWORD *)(v469 + 64);
        if ( v470 - 1 > 0x7FFFFFFE )
        {
          updated = sqlite3CorruptError(98486);
          goto LABEL_487;
        }
        v794 = v8;
        v793 = 0;
        v795 = 0;
        v471 = *(_DWORD *)(*(_QWORD *)(v469 + 136) + 88LL) - *(_DWORD *)(v469 + 56);
        if ( *(unsigned __int16 *)(v469 + 68) <= v471 )
        {
          v471 = *(unsigned __int16 *)(v469 + 68);
        }
        else if ( v471 < 0 )
        {
          v471 = 0;
        }
        v472 = *(_QWORD *)(v469 + 56);
        v791 = v472;
        if ( v470 > v471 )
        {
          LODWORD(v739) = sqlite3VdbeMemFromBtree(v469, 0, v470, v790);
          updated = v739;
          if ( (_DWORD)v739 )
            goto LABEL_487;
          v470 = v792;
          v472 = v791;
        }
        else
        {
          v792 = v470;
          updated = 0;
          v793 = 16400;
          LODWORD(v739) = 0;
        }
        kk = sqlite3VdbeRecordCompareWithSkip(v470, v472, v819, 0);
        v473 = kk;
        if ( v795 )
          kk = vdbeMemClear(v790);
        v20 = v738;
        if ( (*v738 & 1) != 0 )
          v474 = v473 + 1;
        else
          v474 = -v473;
        if ( v474 <= 0 )
          goto LABEL_571;
        goto LABEL_443;
      case 0x2Bu:
      case 0x2Cu:
        v120 = &v9[14 * *((int *)v20 + 1)];
        v121 = *((_WORD *)v120 + 10);
        if ( (v121 & 0x24) != 0 )
        {
          v122 = *(_QWORD *)v120 != 0;
          goto LABEL_392;
        }
        if ( (v121 & 1) != 0 )
        {
          v122 = 2;
          goto LABEL_392;
        }
        if ( (v121 & 8) != 0 )
        {
          _XMM0.m128i_i64[0] = *(_QWORD *)v120;
        }
        else
        {
          if ( (v121 & 0x12) == 0 )
            goto LABEL_391;
          memRealValue(v120);
        }
        if ( *(double *)_XMM0.m128i_i64 != 0.0 )
        {
          v122 = 1;
          goto LABEL_392;
        }
LABEL_391:
        v122 = 0;
LABEL_392:
        v123 = &v9[14 * *((int *)v738 + 2)];
        v124 = *((_WORD *)v123 + 10);
        if ( (v124 & 0x24) != 0 )
        {
          v125 = *(_QWORD *)v123 != 0;
          goto LABEL_403;
        }
        if ( (v124 & 1) != 0 )
        {
          v125 = 2;
          goto LABEL_403;
        }
        if ( (v124 & 8) != 0 )
        {
          _XMM0.m128i_i64[0] = *(_QWORD *)v123;
        }
        else
        {
          if ( (v124 & 0x12) == 0 )
            goto LABEL_402;
          *(double *)_XMM0.m128i_i64 = memRealValue(v123);
        }
        if ( *(double *)_XMM0.m128i_i64 != 0.0 )
        {
          v125 = 1;
          goto LABEL_403;
        }
LABEL_402:
        v125 = 0;
LABEL_403:
        v126 = qword_18010F5E8;
        if ( *v738 != 44 )
          v126 = qword_18010F5F8;
        v127 = *((unsigned __int8 *)v126 + 3 * v122 + v125);
        v128 = 14LL * *((int *)v738 + 3);
        if ( (_BYTE)v127 == 2 )
        {
          kk = LOWORD(v9[v128 + 5]);
          LOWORD(kk) = kk & 0xF240 | 1;
        }
        else
        {
          *(_QWORD *)&v9[v128] = v127;
          kk = LOWORD(v9[v128 + 5]);
          LOWORD(kk) = kk & 0xF240 | 4;
        }
        LOWORD(v9[v128 + 5]) = kk;
        v20 = v738;
        goto LABEL_571;
      case 0x2Eu:
        v513 = &v9[14 * *((int *)v20 + 1)];
        if ( (v513[5] & 0x10) == 0 )
          goto LABEL_1471;
        v514 = *((_QWORD *)v513 + 1);
        v515 = *(_WORD *)(v514 + 50);
        if ( (v515 & 2) == 0 )
        {
          if ( (v515 & 1) == 0 )
            *(_QWORD *)(v514 + 16) = rowSetEntrySort(*(_QWORD *)(v514 + 16), 1);
          *(_WORD *)(v514 + 50) |= 3u;
        }
        v516 = *(__int64 **)(v514 + 16);
        if ( !v516 )
        {
LABEL_1471:
          if ( (v513[5] & 0x9000) != 0 )
            vdbeMemClearExternAndSetNull(v513, 1);
          else
            *((_WORD *)v513 + 10) = 1;
          goto LABEL_1825;
        }
        v517 = *v516;
        v518 = v516[1];
        *(_QWORD *)(v514 + 16) = v518;
        if ( !v518 )
          sqlite3RowSetClear(v514, 1);
        v519 = &v9[14 * *((int *)v738 + 3)];
        if ( (v519[5] & 0x9000) != 0 )
        {
          vdbeReleaseAndSetInt64(&v9[14 * *((int *)v738 + 3)], v517);
        }
        else
        {
          *(_QWORD *)v519 = v517;
          *((_WORD *)v519 + 10) = 4;
        }
        goto LABEL_1826;
      case 0x2Fu:
        kk = *((int *)v20 + 1);
        v520 = *((int *)v20 + 3);
        v521 = *((_DWORD *)v20 + 4);
        v522 = &v9[14 * kk];
        if ( (v522[5] & 0x10) == 0 )
        {
          kk = sqlite3VdbeMemSetRowSet(&v9[14 * kk], 1);
          if ( (_DWORD)kk )
            goto LABEL_1991;
        }
        v523 = 14 * v520;
        v524 = v521 < 0;
        if ( !v521 )
          goto LABEL_1479;
        kk = sqlite3RowSetTest(*((_QWORD *)v522 + 1), (unsigned int)v521, *(_QWORD *)&v9[v523]);
        if ( (_DWORD)kk )
          goto LABEL_1257;
        v524 = v521 < 0;
LABEL_1479:
        if ( !v524 )
          kk = sqlite3RowSetInsert(*((_QWORD *)v522 + 1), *(_QWORD *)&v9[v523]);
        goto LABEL_569;
      case 0x30u:
        v525 = (__int64 *)*((_QWORD *)v20 + 2);
        if ( !*((_WORD *)v20 + 1) )
          goto LABEL_1485;
        kk = v7[33];
        if ( !kk )
          goto LABEL_1485;
        do
        {
          if ( *(_QWORD *)(kk + 48) == v525[4] )
          {
            updated = v739;
            v8 = (_QWORD *)v742;
            v20 += 24;
            v18 = v751;
            goto LABEL_9;
          }
          kk = *(_QWORD *)(kk + 8);
        }
        while ( kk );
LABEL_1485:
        if ( *((_DWORD *)v7 + 70) >= *((_DWORD *)v8 + 44) )
        {
          updated = 1;
          sqlite3VdbeError(v7, "too many levels of trigger recursion");
          goto LABEL_487;
        }
        v526 = &v9[14 * *((int *)v20 + 3)];
        if ( (v526[5] & 0x10) != 0 )
        {
          v531 = (_DWORD *)*((_QWORD *)v526 + 1);
          goto LABEL_1497;
        }
        v527 = *((_DWORD *)v525 + 4);
        v528 = v527 + *((_DWORD *)v525 + 3) + 1;
        if ( v527 )
          v528 = v527 + *((_DWORD *)v525 + 3);
        v529 = (*((_DWORD *)v525 + 2) + 7) / 8 + 8 * (v527 + 7 * (v528 + 2));
        v530 = (_DWORD *)sqlite3DbMallocRawNN(v8, v529);
        v531 = v530;
        if ( !v530 )
          goto LABEL_579;
        memset_0(v530, 0, v529);
        if ( (v526[5] & 0x9000) != 0 || v526[8] )
          vdbeMemClear(v526);
        v7 = a1;
        *((_WORD *)v526 + 10) = 4112;
        *((_QWORD *)v526 + 1) = v531;
        v526[4] = v529;
        *((_QWORD *)v526 + 6) = sqlite3VdbeFrameMemDel;
        *(_QWORD *)v531 = a1;
        v531[22] = v528;
        v531[23] = *((_DWORD *)v525 + 4);
        v532 = v531 + 28;
        v531[19] = ((int)v738 - (int)v741) / 24;
        *((_QWORD *)v531 + 3) = a1[13];
        v531[21] = *((_DWORD *)a1 + 9);
        *((_QWORD *)v531 + 4) = a1[15];
        v531[18] = *((_DWORD *)a1 + 10);
        *((_QWORD *)v531 + 2) = a1[17];
        v531[20] = *((_DWORD *)a1 + 36);
        *((_QWORD *)v531 + 6) = v525[4];
        v533 = &v531[14 * v528 + 28];
        if ( v531 + 28 != v533 )
        {
          do
          {
            *((_WORD *)v532 + 10) = 0;
            *((_QWORD *)v532 + 3) = v8;
            v532 += 14;
          }
          while ( v532 != v533 );
        }
LABEL_1497:
        ++*((_DWORD *)v7 + 70);
        v9 = v531 + 28;
        *((_QWORD *)v531 + 1) = v7[33];
        *((_QWORD *)v531 + 7) = v8[7];
        *((_QWORD *)v531 + 12) = v7[7];
        v746 = v531 + 28;
        *((_QWORD *)v531 + 13) = *(_QWORD *)(*v7 + 120);
        *((_QWORD *)v531 + 8) = v7[37];
        v7[37] = 0;
        v7[7] = 0;
        v7[33] = (__int64)v531;
        v7[13] = (__int64)(v531 + 28);
        v534 = (int)v531[22];
        *((_DWORD *)v7 + 9) = v534;
        *((_DWORD *)v7 + 10) = *((unsigned __int16 *)v531 + 46);
        v535 = (__int64)&v531[14 * v534 + 28];
        v7[15] = v535;
        v536 = (void *)(v535 + 8LL * *((int *)v525 + 4));
        *((_QWORD *)v531 + 5) = v536;
        memset_0(v536, 0, (*((_DWORD *)v525 + 2) + 7) / 8);
        v537 = (unsigned __int8 *)*v525;
        v7[17] = *v525;
        v538 = *((_DWORD *)v525 + 2);
        updated = v739;
        v741 = v537;
        v738 = v537 - 24;
        *((_DWORD *)v7 + 36) = v538;
LABEL_1826:
        kk = *((unsigned int *)v8 + 102);
        if ( (_DWORD)kk )
        {
          v11 = v743;
          goto LABEL_2030;
        }
        v670 = v743;
        if ( v744 >= v743 )
        {
          while ( 1 )
          {
            kk = v8[66];
            if ( !kk )
              break;
            v671 = *((unsigned int *)v8 + 136);
            kk = ((__int64 (__fastcall *)(_QWORD))kk)(v8[67]);
            if ( (_DWORD)kk )
            {
              v154 = (_QWORD *)v742;
              v11 = -1;
              updated = 9;
              goto LABEL_489;
            }
            v670 += v671;
            v743 = v670;
            if ( v744 < v670 )
              goto LABEL_569;
          }
        }
LABEL_1446:
        v10 = v737;
        v20 = v738;
LABEL_571:
        v5 = v741;
LABEL_572:
        v12 = 0x180000000uLL;
LABEL_573:
        v17 = HIDWORD(v739);
LABEL_574:
        v13 = 1;
LABEL_575:
        v8 = (_QWORD *)v742;
        v20 += 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x31u:
        if ( *((_DWORD *)v20 + 1) )
        {
          if ( v8[95] )
            goto LABEL_575;
          if ( v8[96] )
          {
            v8 = (_QWORD *)v742;
            v20 += 24;
            v18 = v751;
            continue;
          }
        }
        else
        {
          if ( v7[10] )
            goto LABEL_575;
          if ( v8[96] )
          {
            v8 = (_QWORD *)v742;
            v20 += 24;
            v18 = v751;
            continue;
          }
        }
        goto LABEL_1260;
      case 0x32u:
        kk = *((int *)v20 + 1);
        if ( (v9[14 * kk + 5] & 1) != 0 )
          goto LABEL_1260;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x33u:
        kk = *((int *)v20 + 1);
        if ( (v9[14 * kk + 5] & 1) == 0 )
          goto LABEL_1260;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x34u:
      case 0x35u:
      case 0x36u:
      case 0x37u:
      case 0x38u:
      case 0x39u:
        v101 = &v9[14 * *((int *)v20 + 1)];
        v102 = *((_WORD *)v101 + 10);
        v103 = &v746[14 * *((int *)v20 + 3)];
        v104 = *((_WORD *)v103 + 10);
        if ( ((unsigned __int8)v102 & (unsigned __int8)v104 & 4) != 0 )
        {
          if ( *(_QWORD *)v103 <= *(_QWORD *)v101 )
          {
            v13 = 1;
            if ( *(_QWORD *)v103 >= *(_QWORD *)v101 )
            {
              kk = (__int64)off_18013C370;
              if ( *((_BYTE *)off_18013C370 + v21) )
                goto LABEL_1260;
              v17 = 0;
            }
            else
            {
              kk = off_18013C368;
              if ( *(_BYTE *)(v21 + off_18013C368) )
                goto LABEL_1260;
              v17 = 0xFFFFFFFFLL;
            }
            HIDWORD(v739) = v17;
            goto LABEL_323;
          }
          kk = (__int64)off_18013C378;
          if ( *((_BYTE *)off_18013C378 + v21) )
            goto LABEL_1259;
          v9 = v746;
          v13 = 1;
          v7 = a1;
          v17 = 1;
          v10 = v737;
          HIDWORD(v739) = 1;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        else
        {
          v105 = v102 | v104;
          if ( (((unsigned __int8)v102 | (unsigned __int8)v104) & 1) == 0 )
          {
            v108 = v20[2] & 0x47;
            if ( v108 < 0x43u )
            {
              if ( v108 == 66 && (v105 & 2) != 0 )
              {
                if ( (v102 & 2) == 0 && (v102 & 0x2C) != 0 )
                {
                  LOBYTE(v17) = 1;
                  sqlite3VdbeMemStringify(v101, v737, v17);
                  v102 = *((_WORD *)v101 + 10) ^ (*((_WORD *)v101 + 10) ^ v102) & 0xDBF;
                  if ( v101 == v103 )
                    v104 = v102 | 2;
                }
                if ( (v104 & 2) == 0 && (v104 & 0x2C) != 0 )
                {
                  LOBYTE(v17) = 1;
                  sqlite3VdbeMemStringify(v103, v737, v17);
                  v104 = *((_WORD *)v103 + 10) ^ (*((_WORD *)v103 + 10) ^ v104) & 0xDBF;
                }
              }
            }
            else if ( (v105 & 2) != 0 )
            {
              if ( (v102 & 0x2E) == 2 )
              {
                applyNumericAffinity(v101, 0);
                v104 = *((_WORD *)v103 + 10);
              }
              if ( (v104 & 0x2E) == 2 )
                applyNumericAffinity(v103, 0);
            }
            v109 = sqlite3MemCompare(v103, v101, *((_QWORD *)v738 + 2));
            v5 = v741;
            v12 = 0x180000000uLL;
            v17 = v109;
            HIDWORD(v739) = v109;
            goto LABEL_349;
          }
          kk = *((unsigned __int16 *)v20 + 1);
          if ( (kk & 0x80u) != 0LL )
          {
            if ( ((unsigned __int8)v102 & (unsigned __int8)v104 & 1) != 0 && (v104 & 0x100) == 0 )
            {
              v17 = 0;
              v106 = *v20;
              kk = (__int64)off_18013C370;
              goto LABEL_354;
            }
            v107 = (v104 & 1) == 0;
            v17 = (unsigned int)(2 * v107 - 1);
            HIDWORD(v739) = 2 * v107 - 1;
LABEL_349:
            if ( (int)v17 >= 0 )
            {
              v106 = *v738;
              if ( (_DWORD)v17 )
                kk = (__int64)off_18013C378;
              else
                kk = (__int64)off_18013C370;
LABEL_354:
              v110 = *(_BYTE *)(v106 + kk);
              HIDWORD(v739) = v17;
            }
            else
            {
              kk = off_18013C368;
              v110 = *(_BYTE *)(*v738 + off_18013C368);
            }
            v20 = v738;
            v195 = v110 == 0;
            *((_WORD *)v103 + 10) = v104;
            v13 = 1;
            *((_WORD *)v101 + 10) = v102;
            if ( !v195 )
              goto LABEL_1260;
LABEL_323:
            v9 = v746;
LABEL_324:
            v7 = a1;
            v10 = v737;
            v8 = (_QWORD *)v742;
            v20 += 24;
            v6 = v744;
            v18 = v751;
            continue;
          }
          if ( (kk & 0x10) != 0 )
            goto LABEL_1260;
          v7 = a1;
          v17 = 1;
          v9 = v746;
          v10 = v737;
          HIDWORD(v739) = 1;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        continue;
      case 0x3Au:
        if ( !(_DWORD)v17 )
          goto LABEL_1260;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x3Bu:
        kk = *((int *)v20 + 1);
        v547 = *(_QWORD *)&v9[14 * kk];
        if ( v547 <= 0 )
          goto LABEL_16;
        *(_QWORD *)&v9[14 * kk] = v547 - *((int *)v738 + 3);
        goto LABEL_1258;
      case 0x3Cu:
        v554 = 14LL * *((int *)v20 + 1);
        kk = *(_QWORD *)&v9[v554];
        if ( !kk )
          goto LABEL_70;
        if ( kk <= 0 )
          goto LABEL_473;
        *(_QWORD *)&v9[v554] = kk - 1;
        v20 = v738;
        goto LABEL_1260;
      case 0x3Du:
        v555 = 14LL * *((int *)v20 + 1);
        kk = *(_QWORD *)&v9[v555];
        if ( kk == 0x8000000000000000uLL )
          goto LABEL_70;
        *(_QWORD *)&v9[v555] = --kk;
        v20 = v738;
        if ( !kk )
          goto LABEL_1260;
        goto LABEL_575;
      case 0x3Eu:
        kk = v8[4];
        v592 = *(_QWORD *)(32LL * *((int *)v20 + 1) + kk + 8);
        v593 = *(_QWORD *)(v592 + 8);
        if ( *(_BYTE *)(v592 + 17) )
        {
          ++*(_DWORD *)(v592 + 20);
          if ( !*(_BYTE *)(v592 + 18) )
            kk = btreeLockCarefully(v592);
        }
        if ( *(_BYTE *)(v593 + 33) )
        {
          v594 = *(_DWORD *)(v593 + 64);
          v595 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v593 + 24) + 80LL) + 36LL));
          kk = finalDbSize(v593, v594, v595);
          v596 = kk;
          if ( v594 < (unsigned int)kk || v595 >= v594 )
          {
            kk = sqlite3_log(
                   11,
                   "%s at line %d of [%.10s]",
                   "database corruption",
                   73618,
                   "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
            updated = 11;
            LODWORD(v739) = 11;
          }
          else if ( v595 )
          {
            v597 = *(_QWORD *)(v593 + 16);
            if ( !v597 || (kk = saveCursorsOnList(v597, 0, 0), LODWORD(v739) = kk, (updated = kk) == 0) )
            {
              for ( j = *(_QWORD *)(v593 + 16); j; j = *(_QWORD *)(j + 40) )
                *(_BYTE *)(j + 1) &= ~4u;
              kk = incrVacuumStep(v593, v596, v594, 0);
              LODWORD(v739) = kk;
              updated = kk;
              if ( !(_DWORD)kk )
              {
                updated = sqlite3PagerWrite(*(_QWORD *)(*(_QWORD *)(v593 + 24) + 112LL));
                LODWORD(v739) = updated;
                kk = *(_QWORD *)(v593 + 24);
                *(_DWORD *)(*(_QWORD *)(kk + 80) + 28LL) = _byteswap_ulong(*(_DWORD *)(v593 + 64));
              }
            }
          }
          else
          {
            updated = 101;
            LODWORD(v739) = 101;
          }
          v7 = a1;
          v9 = v746;
        }
        else
        {
          updated = 101;
          LODWORD(v739) = 101;
        }
        if ( *(_BYTE *)(v592 + 17) )
        {
          v195 = (*(_DWORD *)(v592 + 20))-- == 1;
          if ( v195 )
            kk = unlockBtreeMutex(v592);
        }
        if ( !updated )
          goto LABEL_569;
        if ( updated == 101 )
          goto LABEL_1695;
        goto LABEL_487;
      case 0x3Fu:
        kk = v7[15];
        v666 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        if ( *(_BYTE *)(v666 + 2) )
          goto LABEL_70;
        v667 = *(__int64 ***)(v666 + 48);
        v668 = *v667;
        v669 = **v667;
        LODWORD(v739) = (*(__int64 (__fastcall **)(__int64 **, __int64))(v669 + 72))(v667, 1);
        updated = v739;
        sqlite3VtabImportErrmsg(v7, v668);
        if ( (_DWORD)v739 )
          goto LABEL_487;
        if ( !(*(unsigned int (__fastcall **)(_QWORD))(v669 + 80))(*(_QWORD *)(v666 + 48)) )
          goto LABEL_1825;
        goto LABEL_1826;
      case 0x40u:
        v709 = 14LL * *((int *)v20 + 1);
        v710 = filterHash(v9, v20);
        v5 = v741;
        v711 = *(char *)(((v710 % (8 * v9[v709 + 4])) >> 3) + *(_QWORD *)&v9[v709 + 2]);
        v20 = v738;
        kk = (v710 % (8 * v9[v709 + 4])) & 7;
        v13 = 1;
        if ( !_bittest(&v711, kk) )
        {
          ++*((_DWORD *)v7 + 61);
          goto LABEL_1260;
        }
        ++*((_DWORD *)v7 + 60);
        goto LABEL_108;
      case 0x41u:
      case 0x42u:
        v691 = *((_QWORD *)v20 + 2);
        v692 = &v9[14 * *((int *)v20 + 3)];
        if ( *(_DWORD **)v691 != v692 )
        {
          *(_QWORD *)(v691 + 24) = a1;
          *(_QWORD *)v691 = v692;
          *(_BYTE *)(v691 + 40) = v10;
          v693 = (unsigned int)*(unsigned __int8 *)(v691 + 42) - 1;
          if ( (int)v693 >= 0 )
          {
            do
            {
              *(_QWORD *)(v691 + 8 * v693 + 48) = &v9[14 * (int)v693 + 14 * *((_DWORD *)v20 + 2)];
              v693 = (unsigned int)(v693 - 1);
            }
            while ( (int)v693 >= 0 );
            v8 = (_QWORD *)v742;
          }
        }
        *((_WORD *)v692 + 10) &= 0xF241u;
        *((_WORD *)v692 + 10) |= 1u;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v691 + 8) + 24LL))(
          v691,
          *(unsigned __int8 *)(v691 + 42),
          v691 + 48);
        kk = *(unsigned int *)(v691 + 36);
        if ( !(_DWORD)kk )
        {
          v7 = a1;
          v20 = v738;
          goto LABEL_571;
        }
        if ( (int)kk > 0 )
        {
          v694 = *((_WORD *)v692 + 10);
          v695 = 514;
          if ( (v694 & 0x202) == 0x202 && *((_BYTE *)v692 + 22) == 1 )
          {
            v696 = (const char *)*((_QWORD *)v692 + 1);
          }
          else if ( (v694 & 1) != 0 )
          {
            v696 = 0;
          }
          else
          {
            LOBYTE(v695) = 1;
            v696 = (const char *)valueToText(v692, v695);
          }
          kk = sqlite3VdbeError(a1, "%s", v696);
          updated = *(_DWORD *)(v691 + 36);
          LODWORD(v739) = updated;
        }
        v697 = (unsigned __int64 *)(a1 + 37);
        v698 = a1[37];
        if ( !v698 )
          goto LABEL_1914;
        kk = (__int64)v738;
        v699 = *(_DWORD *)(v691 + 32);
        v700 = *((_DWORD *)v738 + 1);
        while ( 1 )
        {
          if ( v699 < 0
            || *(_DWORD *)v698 == v699
            && (kk = *(unsigned int *)(v698 + 4), (int)kk >= 0)
            && ((int)kk > 31 || !_bittest(&v700, kk)) )
          {
            v701 = *(void (__fastcall **)(_QWORD))(v698 + 16);
            if ( v701 )
              v701(*(_QWORD *)(v698 + 8));
            *v697 = *(_QWORD *)(v698 + 24);
            if ( v698 < v8[62] )
            {
              if ( v698 >= v8[60] )
              {
                kk = v8[59];
                *(_QWORD *)v698 = kk;
                v8[59] = v698;
                goto LABEL_1912;
              }
              if ( v698 >= v8[61] )
              {
                kk = v8[57];
                *(_QWORD *)v698 = kk;
                v8[57] = v698;
                goto LABEL_1912;
              }
            }
            if ( v8[97] )
            {
              kk = measureAllocationSize(v8, v698);
            }
            else
            {
              if ( dword_18013C1B0 )
              {
                if ( (_QWORD)xmmword_18013FC60 )
                  ((void (*)(void))xmmword_18013C230)();
                v702 = ((__int64 (__fastcall *)(unsigned __int64))xmmword_18013C1E8)(v698);
                --qword_18013FBE8;
                qword_18013FBA0 -= v702;
                kk = ((__int64 (__fastcall *)(unsigned __int64))xmmword_18013C1D8)(v698);
                if ( !(_QWORD)xmmword_18013FC60 )
                  goto LABEL_1912;
                v703 = (__int64 (*)(void))xmmword_18013C240;
              }
              else
              {
                v703 = (__int64 (*)(void))xmmword_18013C1D8;
              }
              kk = v703();
            }
          }
          else
          {
            v697 = (unsigned __int64 *)(v698 + 24);
          }
LABEL_1912:
          v698 = *v697;
          if ( !*v697 )
          {
            v9 = v746;
            v10 = v737;
LABEL_1914:
            *(_DWORD *)(v691 + 36) = 0;
            v318 = updated == 0;
            v7 = a1;
            goto LABEL_960;
          }
        }
      case 0x43u:
        kk = 56LL * *((int *)v20 + 1);
        if ( (*((_BYTE *)v9 + kk + 20) & 4) == 0 )
          goto LABEL_70;
        kk = *(_QWORD *)((char *)v9 + kk);
        v8 = (_QWORD *)v742;
        v20 = &v5[24 * kk + 24];
        v18 = v751;
        continue;
      case 0x44u:
        v26 = 14LL * *((int *)v20 + 1);
        v738 = &v5[24 * *(_DWORD *)&v5[24 * *(_QWORD *)&v9[v26] + 8] - 24];
        kk = 0;
        LOWORD(v9[v26 + 5]) = 0;
LABEL_16:
        v20 = v738;
        goto LABEL_574;
      case 0x45u:
        kk = *((int *)v20 + 3);
        if ( (v9[14 * kk + 5] & 1) != 0 )
          goto LABEL_19;
        goto LABEL_70;
      case 0x46u:
LABEL_19:
        v29 = v7[33];
        if ( !v29 || *((_DWORD *)v738 + 1) )
        {
          v718 = *((_DWORD *)v738 + 1);
          *((_DWORD *)v7 + 13) = v718;
          *((_BYTE *)v7 + 196) = v738[8];
          if ( v718 )
          {
            v719 = *((unsigned __int16 *)v738 + 1);
            if ( (_WORD)v719 )
            {
              sqlite3VdbeError(v7, "%s constraint failed", *(const char **)(v12 + 8 * v719 + 1111488));
              if ( *((_QWORD *)v738 + 2) )
                v7[21] = sqlite3MPrintf(v8, "%z: %s", v7[21]);
            }
            else
            {
              sqlite3VdbeError(v7, "%s", *((const char **)v738 + 2));
            }
            sqlite3_log(
              *((unsigned int *)v738 + 1),
              "abort at %d in [%s]: %s",
              (v738 - v741) / 24,
              (const char *)v7[31],
              (const char *)v7[21]);
          }
          v154 = (_QWORD *)v742;
          updated = sqlite3VdbeHalt(v7);
          v11 = v743;
          v155 = v744;
          if ( updated == 5 )
          {
            *((_DWORD *)v7 + 13) = 5;
          }
          else
          {
            updated = 101;
            if ( *((_DWORD *)v7 + 13) )
              updated = 1;
          }
          goto LABEL_2067;
        }
        v7[33] = *(_QWORD *)(v29 + 8);
        --*((_DWORD *)v7 + 70);
        v30 = v7[7];
        v8[15] = v30;
        v8[16] += v30;
        LODWORD(kk) = sqlite3VdbeFrameRestore(v29, 1);
        if ( *((_DWORD *)v738 + 2) == 4 )
          LODWORD(kk) = *(_DWORD *)(v7[17] + 24LL * (int)kk + 8) - 1;
        v5 = (unsigned __int8 *)v7[17];
        v9 = (_DWORD *)v7[13];
        kk = (int)kk;
        v741 = v5;
        v746 = v9;
        v20 = &v5[24 * (int)kk];
        goto LABEL_572;
      case 0x47u:
        v31 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v31 + 20) & 0x9000) != 0 )
        {
          v32 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v31);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v31 = v32;
          v20 = v738;
        }
        else
        {
          *(_WORD *)(v31 + 20) = 4;
        }
        kk = *((int *)v738 + 1);
        *(_QWORD *)v31 = kk;
        goto LABEL_574;
      case 0x48u:
        v33 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v33 + 20) & 0x9000) != 0 )
        {
          v34 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v33);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v33 = v34;
        }
        else
        {
          *(_WORD *)(v33 + 20) = 4;
        }
        goto LABEL_31;
      case 0x49u:
        goto LABEL_54;
      case 0x4Au:
      case 0x4Bu:
        v43 = *((int *)v20 + 2);
        v44 = v7[13] + 56 * v43;
        if ( (*(_WORD *)(v44 + 20) & 0x9000) != 0 )
        {
          v44 = out2PrereleaseWithClear(v7[13] + 56 * v43, 1);
          v13 = 1;
        }
        else
        {
          *(_WORD *)(v44 + 20) = 4;
        }
        kk = 257;
        v20 = v738;
        v45 = *((_DWORD *)v738 + 3) - *((_DWORD *)v738 + 2);
        v46 = 1;
        if ( *((_DWORD *)v738 + 1) )
          v46 = 257;
        *(_WORD *)(v44 + 20) = v46;
        *(_DWORD *)(v44 + 16) = 0;
        if ( v45 <= 0 )
          goto LABEL_106;
        do
        {
          v44 += 56;
          if ( (*(_WORD *)(v44 + 20) & 0x9000) != 0 )
            kk = vdbeMemClearExternAndSetNull(v44, v13);
          --v45;
          *(_WORD *)(v44 + 20) = v46;
          *(_DWORD *)(v44 + 16) = 0;
        }
        while ( v45 > 0 );
        goto LABEL_569;
      case 0x4Cu:
        v47 = 14LL * *((int *)v20 + 1);
        kk = 65473;
        LOWORD(v9[v47 + 5]) &= 0xFFC1u;
        LOWORD(v9[v47 + 5]) |= 1u;
        goto LABEL_70;
      case 0x4Du:
        v48 = *((int *)v20 + 2);
        v49 = v7[13] + 56 * v48;
        if ( (*(_WORD *)(v49 + 20) & 0x9000) != 0 )
          v49 = out2PrereleaseWithClear(v7[13] + 56 * v48, 1);
        else
          *(_WORD *)(v49 + 20) = 4;
        v50 = *((_QWORD *)v738 + 2);
        v51 = *((int *)v738 + 1);
        if ( v50 )
        {
          kk = sqlite3VdbeMemSetStr(v49, v50, v51, 0, 0);
          v20 = v738;
          *(_BYTE *)(v49 + 22) = v10;
          goto LABEL_571;
        }
        if ( (*(_WORD *)(v49 + 20) & 0x9000) != 0 || *(_DWORD *)(v49 + 32) )
          vdbeMemClear(v49);
        *(_WORD *)(v49 + 20) = 1040;
        *(_DWORD *)(v49 + 16) = 0;
        if ( (int)v51 < 0 )
          LODWORD(v51) = 0;
        *(_DWORD *)v49 = v51;
        *(_BYTE *)(v49 + 22) = 1;
        *(_QWORD *)(v49 + 8) = 0;
        kk = sqlite3VdbeMemExpandBlob(v49, v50);
        if ( !(_DWORD)kk )
        {
          v20 = v738;
          *(_BYTE *)(v49 + 22) = v10;
          goto LABEL_571;
        }
        goto LABEL_1991;
      case 0x4Eu:
        v52 = v7[16];
        v53 = 56LL * *((int *)v20 + 1);
        v54 = *(_WORD *)(v53 + v52 - 36);
        if ( (v54 & 0x12) != 0 )
        {
          v55 = *(_DWORD *)(v53 + v52 - 40);
          if ( (v54 & 0x400) != 0 )
            v55 += *(_DWORD *)(v53 + v52 - 56);
          if ( v55 > *(_DWORD *)(*(_QWORD *)(v53 + v52 - 32) + 136LL) )
            goto LABEL_1986;
        }
        v56 = (__m128i *)&v9[14 * *((int *)v738 + 2)];
        if ( (v56[1].m128i_i16[2] & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v738 + 2)], 1);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v13 = 1;
        }
        _XMM0 = *(__m128i *)(v53 + v52 - 56);
        *v56 = _XMM0;
        v56[1].m128i_i64[0] = *(_QWORD *)(v53 + v52 - 40);
        kk = v56[1].m128i_u16[2];
        LOWORD(kk) = kk & 0x8FBF | 0x2040;
        v56[1].m128i_i16[2] = kk;
        goto LABEL_90;
      case 0x4Fu:
        v57 = *((_DWORD *)v20 + 3);
        v58 = &v9[14 * *((int *)v20 + 1)];
        v59 = &v9[14 * *((int *)v20 + 2)];
        while ( 1 )
        {
          if ( (v59[5] & 0x9000) != 0 || v59[8] )
          {
            vdbeMemClear(v59);
            v13 = 1;
          }
          *(_OWORD *)v59 = *(_OWORD *)v58;
          *((_OWORD *)v59 + 1) = *((_OWORD *)v58 + 1);
          _XMM0 = *((__m128i *)v58 + 2);
          *((__m128i *)v59 + 2) = _XMM0;
          *((_QWORD *)v59 + 6) = *((_QWORD *)v58 + 6);
          *((_WORD *)v58 + 10) = 1;
          v58[8] = 0;
          kk = *((unsigned __int16 *)v59 + 10);
          if ( (kk & 0x4000) != 0 )
          {
            if ( (kk & 0x12) != 0
              && ((kk & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v59, 1)
               || (!v59[8] || *((_QWORD *)v59 + 1) != *((_QWORD *)v59 + 5)) && (unsigned int)vdbeMemAddTerminator(v59)) )
            {
              goto LABEL_1991;
            }
            kk = 49151;
            v13 = 1;
            *((_WORD *)v59 + 10) &= ~0x4000u;
          }
          v58 += 14;
          v59 += 14;
          if ( !--v57 )
            goto LABEL_105;
        }
      case 0x50u:
        v60 = *((_DWORD *)v20 + 3);
        v61 = (__m128i *)&v9[14 * *((int *)v20 + 1)];
        v62 = (__m128i *)&v9[14 * *((int *)v20 + 2)];
        while ( 2 )
        {
          if ( (v62[1].m128i_i16[2] & 0x9000) != 0 )
          {
            vdbeClrCopy(v62, v61, 0x4000);
          }
          else
          {
            _XMM0 = *v61;
            *v62 = *v61;
            v62[1].m128i_i64[0] = v61[1].m128i_i64[0];
            if ( (v61[1].m128i_i16[2] & 0x2000) == 0 )
            {
              v62[1].m128i_i16[2] &= 0xCFFFu;
              v62[1].m128i_i16[2] |= 0x4000u;
            }
          }
          kk = v62[1].m128i_u16[2];
          if ( (kk & 0x4000) == 0 )
            goto LABEL_122;
          if ( (kk & 0x12) != 0
            && ((kk & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v62, v13)
             || (!v62[2].m128i_i32[0] || v62->m128i_i64[1] != v62[2].m128i_i64[1])
             && (unsigned int)vdbeMemAddTerminator(v62)) )
          {
            goto LABEL_1991;
          }
          v62[1].m128i_i16[2] &= ~0x4000u;
          kk = v62[1].m128i_u16[2];
LABEL_122:
          v20 = v738;
          if ( (kk & 0x800) != 0 && (v738[2] & 2) != 0 )
          {
            v13 = 63487;
            LOWORD(kk) = kk & 0xF7FF;
            v62[1].m128i_i16[2] = kk;
          }
          if ( v60 )
          {
            --v60;
            v62 = (__m128i *)((char *)v62 + 56);
            v61 = (__m128i *)((char *)v61 + 56);
            continue;
          }
          goto LABEL_570;
        }
      case 0x51u:
        v63 = (__m128i *)&v9[14 * *((int *)v20 + 1)];
        kk = (__int64)&v9[14 * *((int *)v20 + 2)];
        if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
        {
          kk = vdbeClrCopy(&v9[14 * *((int *)v20 + 2)], v63, 0x4000);
          v20 = v738;
          goto LABEL_571;
        }
        _XMM0 = *v63;
        *(__m128i *)kk = *v63;
        *(_QWORD *)(kk + 16) = v63[1].m128i_i64[0];
        v195 = (v63[1].m128i_i16[2] & 0x2000) == 0;
        v13 = 1;
        if ( !v195 )
          goto LABEL_70;
        *(_WORD *)(kk + 20) &= 0xCFFFu;
        *(_WORD *)(kk + 20) |= 0x4000u;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x52u:
        v64 = &v9[14 * *((int *)v20 + 2)];
        kk = *(_QWORD *)&v9[14 * *((int *)v20 + 1)];
        if ( (v64[5] & 0x9000) != 0 )
        {
          kk = vdbeReleaseAndSetInt64(&v9[14 * *((int *)v20 + 2)], *(_QWORD *)&v9[14 * *((int *)v20 + 1)]);
          v20 = v738;
          goto LABEL_571;
        }
        *(_QWORD *)v64 = kk;
        *((_WORD *)v64 + 10) = 4;
        v17 = HIDWORD(v739);
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x53u:
        if ( v7[10] > 0 )
        {
          *((_DWORD *)v7 + 13) = 787;
          *((_BYTE *)v7 + 196) = 2;
          sqlite3VdbeError(v7, "FOREIGN KEY constraint failed");
          updated = ((*((char *)v7 + 198) >> 7) & 0x312) + 1;
          goto LABEL_487;
        }
        updated = 0;
        LODWORD(v739) = 0;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x54u:
        *((_DWORD *)v7 + 11) = (*((_DWORD *)v7 + 11) + 2) | 1;
        v7[20] = (__int64)&v9[14 * *((int *)v20 + 1)];
        if ( *((_BYTE *)v8 + 103) )
          goto LABEL_1991;
        if ( (*((_BYTE *)v8 + 110) & 4) != 0 )
        {
          ((void (__fastcall *)(__int64, _QWORD, __int64 *, _QWORD))v8[31])(4, v8[32], v7, 0);
          LODWORD(v5) = (_DWORD)v741;
        }
        v154 = (_QWORD *)v742;
        updated = 100;
        *((_DWORD *)v7 + 12) = ((int)v738 - (int)v5) / 24 + 1;
        goto LABEL_2066;
      case 0x55u:
        kk = *((int *)v20 + 1);
        if ( !(_DWORD)kk )
          goto LABEL_70;
        kk = (__int64)&v9[14 * kk];
        if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
        {
          kk = vdbeReleaseAndSetInt64(kk, 0);
          v20 = v738;
          goto LABEL_571;
        }
        *(_QWORD *)kk = 0;
        *(_WORD *)(kk + 20) = 4;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x56u:
        v97 = &v9[14 * *((int *)v20 + 1)];
        sqlite3VdbeMemIntegerify(v97, 1);
        v20 = v738;
        kk = *((int *)v738 + 2);
        *v97 += kk;
        goto LABEL_571;
      case 0x57u:
        v99 = 14LL * *((int *)v20 + 1);
        kk = LOWORD(v9[v99 + 5]);
        if ( (kk & 0x24) == 0 )
          goto LABEL_70;
        if ( (kk & 8) != 0 )
          _XMM0.m128i_i64[0] = *(_QWORD *)&v9[v99];
        else
          *(double *)_XMM0.m128i_i64 = (double)(int)*(_QWORD *)&v9[v99];
        *(_QWORD *)&v9[v99] = _XMM0.m128i_i64[0];
        LOWORD(kk) = kk & 0xF240 | 8;
        LOWORD(v9[v99 + 5]) = kk;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v18 = v751;
        continue;
      case 0x58u:
        v100 = &v9[14 * *((int *)v20 + 1)];
        if ( (v100[5] & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(&v9[14 * *((int *)v20 + 1)], 1);
          if ( updated )
          {
            v154 = (_QWORD *)v742;
            v11 = v743;
            v155 = v744;
            goto LABEL_490;
          }
        }
        kk = sqlite3VdbeMemCast(v100, v738[8], v10);
        goto LABEL_959;
      case 0x59u:
      case 0x5Du:
      case 0x7Bu:
        goto LABEL_70;
      case 0x5Au:
        if ( (v20[2] & 1) != 0 )
          v111 = *((_QWORD *)v20 - 1) + 4LL;
        else
          v111 = 0;
        kk = *((unsigned int *)v20 + 3);
        v112 = 0;
        v113 = *((_DWORD *)v20 + 1);
        v114 = *((_QWORD *)v20 + 2);
        v115 = *((_DWORD *)v20 + 2);
        LODWORD(v750) = kk;
        v749 = v113;
        LODWORD(v747) = v115;
        if ( (int)kk <= 0 )
        {
          updated = v739;
          v17 = HIDWORD(v739);
          v8 = (_QWORD *)v742;
          v20 = v738 + 24;
          v18 = v751;
          continue;
        }
        while ( 1 )
        {
          v116 = v111 ? *(_DWORD *)(v111 + 4 * v112) : v112;
          v117 = *(_BYTE *)(v112 + *(_QWORD *)(v114 + 24)) & 1;
          v118 = &v9[14 * (v116 + v115)];
          v119 = &v746[14 * v116 + 14 * v113];
          kk = sqlite3MemCompare(v119, v118, *(_QWORD *)(v114 + 8 * v112 + 32));
          HIDWORD(v739) = kk;
          v17 = (unsigned int)kk;
          if ( (_DWORD)kk )
            break;
          v113 = v749;
          v112 = (unsigned int)(v112 + 1);
          v115 = v747;
          v9 = v746;
          if ( (int)v112 >= (int)v750 )
          {
            updated = v739;
            v12 = 0x180000000uLL;
            v20 = v738;
            v17 = 0;
            v7 = a1;
            v10 = v737;
            v5 = v741;
            goto LABEL_574;
          }
        }
        kk = *(_QWORD *)(v114 + 24);
        if ( (*(_BYTE *)(v112 + kk) & 2) != 0 && ((v119[5] & 1) != 0 || (v118[5] & 1) != 0) )
        {
          v17 = (unsigned int)-(int)v17;
          HIDWORD(v739) = v17;
        }
        updated = v739;
        v12 = 0x180000000uLL;
        v20 = v738;
        v195 = v117 == 0;
        v10 = v737;
        v13 = 1;
        v7 = a1;
        v9 = v746;
        v5 = v741;
        if ( !v195 )
        {
          v17 = (unsigned int)-(int)v17;
          HIDWORD(v739) = v17;
          v8 = (_QWORD *)v742;
          v20 = v738 + 24;
          v6 = v744;
          v18 = v751;
          continue;
        }
        goto LABEL_575;
      case 0x5Bu:
        v129 = (int)sqlite3VdbeBooleanValue(&v9[14 * *((int *)v20 + 1)], *((unsigned int *)v20 + 3))
             ^ (unsigned __int64)*((int *)v20 + 4);
        kk = (__int64)&v9[14 * *((int *)v738 + 2)];
        if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
        {
          kk = vdbeReleaseAndSetInt64(&v9[14 * *((int *)v738 + 2)], v129);
          v20 = v738;
        }
        else
        {
          *(_QWORD *)kk = v129;
          v20 = v738;
          *(_WORD *)(kk + 20) = 4;
        }
        goto LABEL_571;
      case 0x5Cu:
        if ( (v9[14 * *((int *)v20 + 1) + 5] & 1) != 0 || (v9[14 * *((int *)v20 + 3) + 5] & 1) != 0 )
        {
          kk = (__int64)&v9[14 * *((int *)v20 + 2)];
          if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
          {
            kk = vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v20 + 2)], 1);
            v20 = v738;
            goto LABEL_571;
          }
          *(_WORD *)(kk + 20) = 1;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        else
        {
          kk = (__int64)&v9[14 * *((int *)v20 + 2)];
          if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
          {
            kk = vdbeReleaseAndSetInt64(&v9[14 * *((int *)v20 + 2)], 0);
            v20 = v738;
            goto LABEL_571;
          }
          *(_QWORD *)kk = 0;
          *(_WORD *)(kk + 20) = 4;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        continue;
      case 0x5Eu:
        v148 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v149 = *((_DWORD *)v20 + 2);
        while ( 2 )
        {
          v749 = v149;
LABEL_476:
          v150 = *(unsigned int **)(v148 + 88);
          v151 = *((_DWORD *)a1 + 11);
          v756 = v150;
          if ( *(_DWORD *)(v148 + 32) == v151 )
          {
            if ( !**(_BYTE **)(v148 + 48) )
              goto LABEL_507;
          }
          else
          {
            if ( *(_BYTE *)(v148 + 2) )
            {
              if ( *(_BYTE *)v148 != 3 || (v159 = *(int *)(v148 + 36), (int)v159 <= 0) )
              {
                v9 = v746;
                kk = (__int64)&v746[14 * *((int *)v738 + 3)];
                if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
                {
                  kk = vdbeMemClearExternAndSetNull(&v746[14 * *((int *)v738 + 3)], v13);
                  v7 = a1;
                  goto LABEL_569;
                }
                v13 = 1;
                v7 = a1;
                *(_WORD *)(kk + 20) = 1;
LABEL_105:
                v20 = v738;
LABEL_106:
                v10 = v737;
                goto LABEL_107;
              }
              v160 = 14 * v159;
              v161 = v746[14 * v159 + 4];
              *(_DWORD *)(v148 + 108) = v161;
              *(_DWORD *)(v148 + 104) = v161;
              v158 = *(unsigned __int8 **)&v746[v160 + 2];
              goto LABEL_501;
            }
            v152 = *(_QWORD *)(v148 + 48);
            if ( *(_BYTE *)(v148 + 3) )
            {
              v13 = *(_QWORD *)(v148 + 16);
              if ( v13 )
              {
                v153 = *(_DWORD *)(v13 + 4LL * (v149 + 1));
                if ( v153 )
                {
                  v148 = *(_QWORD *)(v148 + 40);
                  v149 = v153 - 1;
                  continue;
                }
              }
              LODWORD(v739) = sqlite3VdbeFinishMoveto(v148, v13);
              updated = v739;
              if ( (_DWORD)v739 )
                goto LABEL_486;
              goto LABEL_493;
            }
            if ( !*(_BYTE *)v152 )
            {
LABEL_493:
              getCellInfo(v152);
              *(_DWORD *)(v148 + 104) = *(_DWORD *)(v152 + 64);
              v156 = *(unsigned __int16 *)(v152 + 68);
              v157 = *(_DWORD *)(*(_QWORD *)(v152 + 136) + 88LL) - *(_DWORD *)(v152 + 56);
              if ( v156 <= v157 )
              {
                *(_DWORD *)(v148 + 108) = v156;
                v158 = *(unsigned __int8 **)(v152 + 56);
              }
              else
              {
                if ( v157 < 0 )
                  v157 = 0;
                *(_DWORD *)(v148 + 108) = v157;
                v158 = *(unsigned __int8 **)(v152 + 56);
              }
LABEL_501:
              *(_QWORD *)(v148 + 96) = v158;
              *(_DWORD *)(v148 + 32) = *((_DWORD *)a1 + 11);
              v162 = *v158;
              *v150 = v162;
              if ( v162 >= 0x80 )
                Varint32 = (unsigned __int8)sqlite3GetVarint32(*(_QWORD *)(v148 + 96), v150);
              else
                Varint32 = 1;
              *(_DWORD *)(v148 + 64) = Varint32;
              *(_WORD *)(v148 + 74) = 0;
              if ( *(_DWORD *)(v148 + 108) >= *v150 )
              {
                v164 = *(_QWORD *)(v148 + 96);
                goto LABEL_523;
              }
              *(_QWORD *)(v148 + 96) = 0;
              *(_DWORD *)(v148 + 108) = 0;
              if ( *v150 > 0x18003 || *v150 > *(_DWORD *)(v148 + 104) )
                goto LABEL_552;
LABEL_507:
              if ( *(unsigned __int16 *)(v148 + 74) > v149 )
              {
                LODWORD(v172) = *(_DWORD *)(v148 + 4LL * v149 + 120);
                goto LABEL_561;
              }
              if ( *(_DWORD *)(v148 + 64) >= *v150 )
              {
                LODWORD(v172) = 0;
                goto LABEL_541;
              }
              v164 = *(_QWORD *)(v148 + 96);
              v747 = v164;
              if ( v164 )
                goto LABEL_524;
              _XMM0.m128i_i64[0] = 0;
              v765 = 0;
              v768 = 0;
              v766 = 0;
              v767 = 0;
              v165 = *(_QWORD *)(v148 + 48);
              v166 = *v150;
              v167 = *(_DWORD *)(*(_QWORD *)(v165 + 136) + 88LL) - *(_DWORD *)(v165 + 56);
              if ( *(unsigned __int16 *)(v165 + 68) <= v167 )
              {
                v167 = *(unsigned __int16 *)(v165 + 68);
              }
              else if ( v167 < 0 )
              {
                v167 = 0;
              }
              v164 = *(_QWORD *)(v165 + 56);
              v747 = v164;
              *((_QWORD *)&v765 + 1) = v164;
              if ( (unsigned int)v166 <= v167 )
              {
                LODWORD(v766) = v166;
                WORD2(v766) = 16400;
                LODWORD(v739) = 0;
                goto LABEL_524;
              }
              LODWORD(v739) = sqlite3VdbeMemFromBtree(v165, 0, v166, &v765);
              updated = v739;
              if ( (_DWORD)v739 )
                goto LABEL_486;
              v164 = *((_QWORD *)&v765 + 1);
LABEL_523:
              v747 = v164;
LABEL_524:
              v168 = *(unsigned __int16 *)(v148 + 74);
              v169 = (unsigned __int8 *)(v164 + *(unsigned int *)(v148 + 64));
              v170 = v164 + *v150;
              v171 = v150[v168];
              while ( 1 )
              {
                v172 = *v169;
                LODWORD(v750) = v172;
                *(_DWORD *)(v148 + 4LL * (int)v168 + 120) = v172;
                if ( (unsigned int)v172 >= 0x80 )
                {
                  v174 = sqlite3GetVarint32(v169, &v750);
                  v172 = (unsigned int)v750;
                  v169 += v174;
                  *(_DWORD *)(v148 + 4LL * (int)v168 + 120) = (_DWORD)v750;
                  v173 = (unsigned int)v172 < 0x80
                       ? *((unsigned __int8 *)qword_180114980 + v172)
                       : (unsigned int)(v172 - 12) >> 1;
                }
                else
                {
                  ++v169;
                  v173 = *((unsigned __int8 *)qword_180114980 + v172);
                }
                v150 = v756;
                v171 += v173;
                LODWORD(v168) = v168 + 1;
                v756[(int)v168] = v171;
                if ( (unsigned int)v168 > v749 )
                  break;
                if ( (unsigned __int64)v169 >= v170 )
                  goto LABEL_534;
              }
              if ( (unsigned __int64)v169 < v170 )
              {
                if ( v171 <= *(unsigned int *)(v148 + 104) )
                  goto LABEL_536;
              }
              else
              {
LABEL_534:
                if ( (unsigned __int64)v169 <= v170 && v171 == *(_DWORD *)(v148 + 104) )
                  goto LABEL_536;
              }
              if ( !*v150 )
              {
                LOWORD(v168) = 0;
                LODWORD(v169) = v170;
LABEL_536:
                v175 = (_DWORD)v169 - v747;
                *(_WORD *)(v148 + 74) = v168;
                *(_DWORD *)(v148 + 64) = v175;
                if ( !*(_QWORD *)(v148 + 96) && ((WORD2(v766) & 0x9000) != 0 || (_DWORD)v767) )
                  vdbeMemClear(&v765);
                v149 = v749;
                v8 = (_QWORD *)v742;
LABEL_541:
                if ( *(unsigned __int16 *)(v148 + 74) <= v149 )
                {
                  v9 = v746;
                  kk = (__int64)&v746[14 * *((int *)v738 + 3)];
                  if ( v738[1] == 0xF6 )
                  {
                    v176 = (__m128i *)*((_QWORD *)v738 + 2);
                    if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
                    {
                      kk = vdbeClrCopy(&v746[14 * *((int *)v738 + 3)], *((_QWORD *)v738 + 2), 0x2000);
                      updated = v739;
                      v7 = a1;
                      goto LABEL_569;
                    }
                    _XMM0 = *v176;
                    updated = v739;
                    v7 = a1;
                    v10 = v737;
                    *(__m128i *)kk = *v176;
                    *(_QWORD *)(kk + 16) = v176[1].m128i_i64[0];
                    if ( (v176[1].m128i_i16[2] & 0x2000) == 0 )
                    {
                      *(_WORD *)(kk + 20) &= 0xAFFFu;
                      *(_WORD *)(kk + 20) |= 0x2000u;
                      v20 = v738;
                      goto LABEL_571;
                    }
LABEL_894:
                    v20 = v738;
                    goto LABEL_571;
                  }
                  if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
                  {
                    kk = vdbeMemClearExternAndSetNull(&v746[14 * *((int *)v738 + 3)], 36864);
                    updated = v739;
                    v7 = a1;
                    goto LABEL_569;
                  }
                  updated = v739;
                  v13 = 1;
                  v7 = a1;
                  *(_WORD *)(kk + 20) = 1;
                  goto LABEL_105;
                }
LABEL_561:
                v178 = v738;
                v179 = (__int64)&v746[14 * *((int *)v738 + 3)];
                if ( (*(_WORD *)(v179 + 20) & 0x9000) != 0 )
                {
                  vdbeMemClearExternAndSetNull(&v746[14 * *((int *)v738 + 3)], v738);
                  v178 = v738;
                }
                if ( *(_DWORD *)(v148 + 108) < v150[v149 + 1] )
                {
                  *(_BYTE *)(v179 + 22) = v737;
                  v184 = v178[2] & 0xC0;
                  if ( !v184 || v184 != (char)0x80 && ((unsigned int)v172 < 0xC || (v172 & 1) != 0 && v184 != -64) )
                  {
                    if ( (unsigned int)v172 < 0x80
                       ? *((unsigned __int8 *)qword_180114980 + (unsigned int)v172)
                       : (unsigned int)(v172 - 12) >> 1 )
                    {
                      kk = vdbeColumnFromOverflow(v148, v149, v172, v150[v149], *((_DWORD *)a1 + 11), v751, v179);
                      LODWORD(v739) = kk;
                      updated = kk;
                      if ( (_DWORD)kk )
                      {
                        v154 = (_QWORD *)v742;
                        v7 = a1;
                        if ( (_DWORD)kk == 7 )
                          goto LABEL_581;
                        if ( (_DWORD)kk != 18 )
                          goto LABEL_488;
                        goto LABEL_1985;
                      }
                      goto LABEL_567;
                    }
                  }
                  v181 = &qword_1801147A0;
                }
                else
                {
                  v180 = (void *)(*(_QWORD *)(v148 + 96) + v150[v149]);
                  if ( (unsigned int)v172 >= 0xC )
                  {
                    v182 = (unsigned int)(v172 - 12) >> 1;
                    *(_DWORD *)(v179 + 16) = v182;
                    *(_BYTE *)(v179 + 22) = v737;
                    v183 = (unsigned int)(v182 + 2);
                    if ( *(_DWORD *)(v179 + 32) >= (int)v183 )
                    {
                      *(_QWORD *)(v179 + 8) = *(_QWORD *)(v179 + 40);
                    }
                    else
                    {
                      if ( (int)v182 > *((_DWORD *)v8 + 34) )
                        goto LABEL_1983;
                      *(_WORD *)(v179 + 20) = 1;
                      if ( (unsigned int)sqlite3VdbeMemGrow(v179, v183, 0) )
                        goto LABEL_579;
                    }
                    memcpy_0(*(void **)(v179 + 8), v180, (unsigned int)(v172 - 12) >> 1);
                    v12 = 0x180000000uLL;
                    updated = v739;
                    v20 = v738;
                    v7 = a1;
                    v9 = v746;
                    v5 = v741;
                    *(_BYTE *)(v182 + *(_QWORD *)(v179 + 8)) = 0;
                    *(_BYTE *)(*(_QWORD *)(v179 + 8) + v182 + 1) = 0;
                    kk = (unsigned __int16)word_18010F614[v172 & 1];
                    *(_WORD *)(v179 + 20) = kk;
                    v10 = v737;
                    goto LABEL_573;
                  }
                  v181 = (__int64 *)v180;
                }
                kk = sqlite3VdbeSerialGet(v181, (unsigned int)v172, v179);
                updated = v739;
LABEL_567:
                v7 = a1;
LABEL_568:
                v9 = v746;
                goto LABEL_569;
              }
              if ( !*(_QWORD *)(v148 + 96) && ((WORD2(v766) & 0x9000) != 0 || (_DWORD)v767) )
                vdbeMemClear(&v765);
LABEL_552:
              v5 = v741;
              v177 = *((_DWORD *)v741 + 3);
              if ( v177 <= 0 )
              {
                updated = sqlite3CorruptError(94960);
                goto LABEL_486;
              }
              v7 = a1;
              v9 = v746;
              v10 = v737;
              kk = 3LL * (v177 - 1);
              v20 = &v741[8 * kk];
              updated = v739;
              goto LABEL_572;
            }
          }
          break;
        }
        LODWORD(v739) = sqlite3VdbeHandleMovedCursor(v148, v13);
        updated = v739;
        if ( (_DWORD)v739 )
          goto LABEL_486;
        goto LABEL_476;
      case 0x5Fu:
        v186 = 0;
        v187 = *((_QWORD *)v20 + 2);
        v188 = *(_QWORD *)(v187 + 8);
        kk = 0;
        v189 = &v9[14 * *((int *)v20 + 1)];
        if ( *(__int16 *)(v187 + 54) <= 0 )
          goto LABEL_324;
        while ( 1 )
        {
          v190 = *(_WORD *)(v188 + 24LL * v186 + 18);
          if ( (v190 & 0x60) == 0 )
            goto LABEL_603;
          if ( (v190 & 0x20) == 0 )
            break;
LABEL_638:
          kk = (unsigned int)*(__int16 *)(v187 + 54);
          if ( ++v186 >= (int)kk )
          {
            v7 = a1;
            goto LABEL_105;
          }
        }
        if ( *((_DWORD *)v738 + 3) )
          goto LABEL_637;
LABEL_603:
        v191 = *(_BYTE *)(v188 + 24LL * v186 + 12);
        if ( v191 >= 67 )
        {
          v192 = *((_WORD *)v189 + 10);
          if ( (v192 & 4) == 0 )
          {
            if ( (v192 & 0x28) != 0 )
            {
              if ( v191 <= 69 )
                sqlite3VdbeIntegerAffinity(v189, 1);
            }
            else if ( (v192 & 2) != 0 )
            {
              applyNumericAffinity(v189, 1);
            }
          }
LABEL_617:
          v194 = *((_WORD *)v189 + 10);
          if ( (v194 & 1) != 0 )
            goto LABEL_636;
          switch ( (*(_DWORD *)(v188 + 24LL * v186 + 8) >> 4) & 0xF )
          {
            case 2:
              v195 = (v194 & 0x10) == 0;
              break;
            case 3:
            case 4:
              v195 = (v194 & 4) == 0;
              break;
            case 5:
              if ( (v194 & 4) != 0 )
              {
                v196 = *(double *)v189;
                if ( (unsigned __int64)(*(_QWORD *)v189 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                {
                  *(double *)_XMM0.m128i_i64 = (double)SLODWORD(v196);
                  v198 = v194 | 8;
                  v197 = v194 | 8;
                  *(double *)v189 = (double)SLODWORD(v196);
                }
                else
                {
                  v197 = v194 | 0x20;
                  v198 = v197;
                }
                *((_WORD *)v189 + 10) = v197;
                *((_WORD *)v189 + 10) = v198 & 0xFFFB;
                goto LABEL_636;
              }
              v195 = (v194 & 0x28) == 0;
              break;
            case 6:
              v195 = (v194 & 2) == 0;
              break;
            default:
LABEL_636:
              v13 = 1;
LABEL_637:
              v189 += 14;
              goto LABEL_638;
          }
          if ( v195 )
          {
            v720 = *(const char **)v187;
            v7 = a1;
            sqlite3VdbeError(
              a1,
              "cannot store %s value in %s column %s.%s",
              (const char *)qword_18013D420[*((unsigned __int8 *)qword_18010E020 + (v194 & 0x3F))],
              off_18013C388[((*(_DWORD *)(v188 + 24LL * v186 + 8) >> 4) & 0xFu) - 1],
              v720,
              *(const char **)(v188 + 24LL * v186));
            v154 = (_QWORD *)v742;
            updated = 3091;
            goto LABEL_488;
          }
          goto LABEL_636;
        }
        if ( v191 != 66 )
          goto LABEL_617;
        v193 = *((_WORD *)v189 + 10);
        if ( (v193 & 2) != 0 || (v193 & 0x2C) == 0 )
          goto LABEL_616;
        if ( (int)v189[8] >= 32 )
        {
          *((_QWORD *)v189 + 1) = *((_QWORD *)v189 + 5);
          *((_WORD *)v189 + 10) = v193 & 0x2D;
        }
        else if ( (unsigned int)sqlite3VdbeMemGrow(v189, 32, 0) )
        {
          *((_BYTE *)v189 + 22) = 0;
LABEL_616:
          *((_WORD *)v189 + 10) &= 0xFFD3u;
          goto LABEL_617;
        }
        vdbeMemRenderNum(32, *((_QWORD *)v189 + 1), v189);
        *((_BYTE *)v189 + 22) = 1;
        *((_WORD *)v189 + 10) = v189[5] & 0xFDD1 | 0x202;
        if ( v737 != 1 )
          sqlite3VdbeMemTranslate(v189, v737);
        goto LABEL_616;
      case 0x60u:
        v199 = (_BYTE *)*((_QWORD *)v20 + 2);
        LOBYTE(kk) = *v199;
        v200 = &v9[14 * *((int *)v20 + 1)];
        while ( 2 )
        {
          if ( (char)kk >= 67 )
          {
            v201 = *((_WORD *)v200 + 10);
            if ( (v201 & 4) == 0 )
            {
              if ( (v201 & 0x28) != 0 )
              {
                if ( (char)kk <= 69 )
                  sqlite3VdbeIntegerAffinity(v200, 1);
              }
              else if ( (v201 & 2) != 0 )
              {
                applyNumericAffinity(v200, 1);
              }
            }
LABEL_655:
            if ( *v199 == 69 )
            {
              v203 = *((_WORD *)v200 + 10);
              if ( (v203 & 4) != 0 )
              {
                v204 = *(double *)v200;
                if ( (unsigned __int64)(*(_QWORD *)v200 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
                {
                  *(double *)_XMM0.m128i_i64 = (double)SLODWORD(v204);
                  v205 = v203 & 0xFFF1 | 8;
                  *(double *)v200 = (double)SLODWORD(v204);
                }
                else
                {
                  v205 = v203 & 0xFFDB | 0x20;
                }
                *((_WORD *)v200 + 10) = v205;
              }
            }
            kk = (unsigned __int8)*++v199;
            if ( (_BYTE)kk )
            {
              v200 += 14;
              continue;
            }
            goto LABEL_894;
          }
          break;
        }
        if ( (_BYTE)kk != 66 )
          goto LABEL_655;
        v202 = *((_WORD *)v200 + 10);
        if ( (v202 & 2) != 0 || (v202 & 0x2C) == 0 )
          goto LABEL_654;
        if ( (int)v200[8] >= 32 )
        {
          *((_QWORD *)v200 + 1) = *((_QWORD *)v200 + 5);
          *((_WORD *)v200 + 10) = v202 & 0x2D;
        }
        else if ( (unsigned int)sqlite3VdbeMemGrow(v200, 32, 0) )
        {
          *((_BYTE *)v200 + 22) = 0;
LABEL_654:
          *((_WORD *)v200 + 10) &= 0xFFD3u;
          goto LABEL_655;
        }
        vdbeMemRenderNum(32, *((_QWORD *)v200 + 1), v200);
        *((_BYTE *)v200 + 22) = 1;
        *((_WORD *)v200 + 10) = v200[5] & 0xFDD1 | 0x202;
        if ( v10 != 1 )
          sqlite3VdbeMemTranslate(v200, v10);
        goto LABEL_654;
      case 0x61u:
        v206 = 0;
        v207 = 0;
        v208 = 0;
        v209 = (_BYTE *)*((_QWORD *)v20 + 2);
        v210 = &v746[14 * *((int *)v20 + 1)];
        v211 = *((_DWORD *)v20 + 3);
        v212 = (int *)&v210[14 * *((_DWORD *)v20 + 2) - 14];
        v756 = v210;
        v750 = v212;
        LODWORD(v747) = v211;
        if ( v209 )
        {
          v213 = v210;
          do
          {
            applyAffinity(v213, (unsigned __int8)*v209, v737);
            if ( *v209 == 69 )
            {
              v214 = *((_WORD *)v213 + 10);
              if ( (v214 & 4) != 0 )
                *((_WORD *)v213 + 10) = v214 & 0xFFDB | 0x20;
            }
            ++v209;
            v213 += 14;
          }
          while ( *v209 );
          v210 = v756;
          LODWORD(v13) = 1;
          v212 = v750;
        }
        v215 = v212;
        while ( 2 )
        {
          v216 = *((unsigned __int16 *)v215 + 10);
          if ( (v216 & 1) != 0 )
          {
            v215[9] = (v216 & 0x400) != 0 ? 0xA : 0;
            ++v207;
          }
          else if ( (v216 & 0x24) != 0 )
          {
            v217 = *(_QWORD *)v215;
            v13 = *(_QWORD *)v215;
            if ( *(__int64 *)v215 < 0 )
              v13 = ~v13;
            ++v207;
            if ( v13 > 0x7F )
            {
              if ( v13 > 0x7FFF )
              {
                if ( v13 > 0x7FFFFF )
                {
                  if ( v13 > 0x7FFFFFFF )
                  {
                    if ( v13 > 0x7FFFFFFFFFFFLL )
                    {
                      v206 += 8;
                      if ( (v216 & 0x20) != 0 )
                      {
                        *(double *)_XMM0.m128i_i64 = (double)(int)v217;
                        v218 = 7;
                        *(double *)v215 = (double)(int)v217;
                        *((_WORD *)v215 + 10) = v216 & 0xFFD7 | 8;
                      }
                      else
                      {
                        v218 = 6;
                      }
                    }
                    else
                    {
                      v206 += 6;
                      v218 = 5;
                    }
                  }
                  else
                  {
                    v206 += 4;
                    v218 = 4;
                  }
                }
                else
                {
                  v206 += 3;
                  v218 = 3;
                }
              }
              else
              {
                v206 += 2;
                v218 = 2;
              }
              v215[9] = v218;
              LODWORD(v13) = 1;
            }
            else if ( (*(_QWORD *)v215 & 1LL) == v217 && *((_BYTE *)a1 + 197) >= 4u )
            {
              v215[9] = v13 + 8;
              LODWORD(v13) = 1;
            }
            else
            {
              LODWORD(v13) = 1;
              ++v206;
              v215[9] = 1;
            }
          }
          else if ( (v216 & 8) != 0 )
          {
            ++v207;
            v215[9] = 7;
            v206 += 8;
          }
          else
          {
            v219 = v215[4];
            v220 = ((v216 >> 1) & 1) + 2 * (v219 + 6);
            if ( (v216 & 0x400) != 0 )
            {
              v221 = *v215;
              v220 += 2 * v221;
              if ( v206 )
              {
                if ( (unsigned int)sqlite3VdbeMemExpandBlob(v215, 1) )
                  goto LABEL_579;
                v219 += *v215;
                LODWORD(v13) = 1;
              }
              else
              {
                v208 += v221;
              }
            }
            v222 = 1;
            v206 += v219;
            for ( k = (unsigned __int64)v220 >> 7; k; k >>= 7 )
              ++v222;
            v207 += v222;
            v215[9] = v220;
          }
          if ( v215 != (int *)v210 )
          {
            v215 -= 14;
            continue;
          }
          break;
        }
        v224 = &v746[14 * (int)v747];
        if ( v207 <= 126 )
          goto LABEL_714;
        for ( m = (unsigned __int64)v207 >> 7; m; m >>= 7 )
          LODWORD(v13) = v13 + 1;
        v207 += v13;
        v226 = 1;
        for ( n = (unsigned __int64)v207 >> 7; n; n >>= 7 )
          ++v226;
        if ( (int)v13 < v226 )
LABEL_714:
          ++v207;
        v228 = (int)v224[8];
        v229 = v206 + v207;
        if ( v229 + v208 <= v228 )
          goto LABEL_720;
        v154 = (_QWORD *)v742;
        if ( v229 + v208 > *(int *)(v742 + 136) )
          goto LABEL_1984;
        if ( (int)v228 >= (int)v229 )
        {
LABEL_720:
          *((_QWORD *)v224 + 1) = *((_QWORD *)v224 + 5);
        }
        else if ( (unsigned int)sqlite3VdbeMemGrow(&v746[14 * (int)v747], (unsigned int)v229, 0) )
        {
          goto LABEL_580;
        }
        v224[4] = v229;
        *((_WORD *)v224 + 10) = 16;
        if ( v208 )
        {
          *v224 = v208;
          *((_WORD *)v224 + 10) = 1040;
        }
        v230 = (_BYTE *)*((_QWORD *)v224 + 1);
        v231 = &v230[v207];
        if ( v207 >= 128 )
        {
          if ( (unsigned int)v207 > 0x3FFF )
          {
            v233 = putVarint64(*((_QWORD *)v224 + 1), v207);
          }
          else
          {
            v233 = 2;
            *v230 = ((unsigned __int64)v207 >> 7) | 0x80;
            v230[1] = v207 & 0x7F;
          }
          v232 = &v230[v233];
        }
        else
        {
          *v230 = v207;
          v232 = v230 + 1;
        }
        v234 = (unsigned int *)v750;
        while ( 1 )
        {
          kk = v210[9];
          if ( (unsigned int)kk > 7 )
          {
            if ( (unsigned int)kk >= 0x80 )
            {
              if ( (unsigned __int64)kk > 0x3FFF )
              {
                v238 = putVarint64(v232, v210[9]);
              }
              else
              {
                *v232 = ((unsigned __int64)kk >> 7) | 0x80;
                v232[1] = kk & 0x7F;
                v238 = 2;
              }
              v232 += v238;
              kk = (int)v210[4];
              if ( (_DWORD)kk )
              {
LABEL_744:
                memcpy_0(v231, *((const void **)v210 + 1), kk);
                kk = (int)v210[4];
                v231 += kk;
              }
            }
            else
            {
              *v232++ = kk;
              if ( (unsigned int)kk >= 0xE )
              {
                kk = (int)v210[4];
                if ( (int)kk > 0 )
                  goto LABEL_744;
              }
            }
          }
          else
          {
            *v232++ = kk;
            if ( (_DWORD)kk )
            {
              v235 = *(_QWORD *)v210;
              v236 = *((unsigned __int8 *)qword_180114980 + kk);
              v237 = (unsigned int)(v236 - 1);
              v231[v237] = *(_QWORD *)v210;
              if ( (_DWORD)v236 != 1 )
              {
                do
                {
                  v235 >>= 8;
                  v195 = (_DWORD)v237 == 1;
                  v237 = (unsigned int)(v237 - 1);
                  v231[v237] = v235;
                }
                while ( !v195 );
                v234 = (unsigned int *)v750;
              }
              v231 += v236;
            }
          }
          if ( v210 == v234 )
          {
            updated = v739;
            v7 = a1;
            v9 = v746;
            v10 = v737;
            v20 = v738;
            goto LABEL_571;
          }
          v210 += 14;
        }
      case 0x62u:
        v239 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 48LL);
        if ( *((_DWORD *)v20 + 3) )
        {
          v241 = sqlite3BtreeRowCountEst(v239);
          goto LABEL_768;
        }
        v242 = moveToRoot(v239, 1);
        v241 = 0;
        LODWORD(v739) = v242;
        updated = v242;
        if ( v242 == 16 )
        {
          updated = 0;
          LODWORD(v739) = 0;
          goto LABEL_768;
        }
        if ( v242 )
          goto LABEL_766;
        while ( 1 )
        {
          if ( *((_DWORD *)v8 + 102) )
            goto LABEL_766;
          v243 = *(_QWORD *)(v239 + 136);
          v244 = *(_BYTE *)(v243 + 8);
          if ( v244 || !*(_BYTE *)(v243 + 1) )
            v241 += *(unsigned __int16 *)(v243 + 24);
          if ( v244 )
            break;
LABEL_761:
          v246 = *(unsigned __int16 *)(v239 + 86);
          v247 = *(_QWORD *)(v243 + 80);
          if ( v246 == *(unsigned __int16 *)(v243 + 24) )
            v248 = *(_DWORD *)(*(unsigned __int8 *)(v243 + 9) + v247 + 8);
          else
            v248 = *(_DWORD *)((unsigned __int16)(*(_WORD *)(v243 + 26)
                                                & __ROR2__(
                                                    *(_WORD *)((unsigned int)(2 * v246) + *(_QWORD *)(v243 + 96)),
                                                    8))
                             + v247);
          v249 = moveToChild(v239, _byteswap_ulong(v248));
          LODWORD(v739) = v249;
          updated = v249;
          if ( v249 )
          {
            LODWORD(v739) = v249;
LABEL_766:
            v241 = 0;
LABEL_767:
            if ( updated )
              goto LABEL_487;
LABEL_768:
            v250 = 56LL * *((int *)v738 + 2) + v7[13];
            if ( (*(_WORD *)(v250 + 20) & 0x9000) != 0 )
            {
              *(_QWORD *)out2PrereleaseWithClear(56LL * *((int *)v738 + 2) + v7[13], v240) = v241;
            }
            else
            {
              *(_WORD *)(v250 + 20) = 4;
              *(_QWORD *)v250 = v241;
            }
            goto LABEL_1826;
          }
        }
        while ( *(_BYTE *)(v239 + 84) )
        {
          moveToParent(v239);
          v243 = *(_QWORD *)(v239 + 136);
          v245 = *(_WORD *)(v239 + 86);
          if ( v245 < *(_WORD *)(v243 + 24) )
          {
            *(_WORD *)(v239 + 86) = v245 + 1;
            goto LABEL_761;
          }
        }
        updated = moveToRoot(v239, v240);
        LODWORD(v739) = updated;
        goto LABEL_767;
      case 0x63u:
        sqlite3BtreeGetMeta(*(_QWORD *)(32LL * *((int *)v20 + 1) + v8[4] + 8), *((unsigned int *)v20 + 3), &v758);
        v282 = v7[13] + 56LL * *((int *)v738 + 2);
        if ( (*(_WORD *)(v282 + 20) & 0x9000) != 0 )
        {
          v283 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v738 + 2), v282);
          v20 = v738;
          v284 = (_QWORD *)v283;
          kk = v758;
          *v284 = v758;
          goto LABEL_571;
        }
        kk = v758;
        *(_WORD *)(v282 + 20) = 4;
        *(_QWORD *)v282 = kk;
        goto LABEL_894;
      case 0x64u:
        v285 = v8[4];
        v286 = 32LL * *((int *)v20 + 1);
        updated = sqlite3BtreeUpdateMeta(
                    *(_QWORD *)(v286 + v285 + 8),
                    *((unsigned int *)v20 + 2),
                    *((unsigned int *)v20 + 3));
        LODWORD(v739) = updated;
        kk = *((unsigned int *)v738 + 2);
        if ( (_DWORD)kk == 1 )
        {
          **(_DWORD **)(v286 + v285 + 24) = *((_DWORD *)v738 + 3) - *((unsigned __int16 *)v738 + 1);
          *((_DWORD *)v8 + 11) |= 1u;
          kk = v8[4];
          for ( ii = *(_QWORD **)(*(_QWORD *)(32LL * *((int *)v738 + 1) + kk + 24) + 16LL); ii; ii = (_QWORD *)*ii )
          {
            v288 = ii[2];
            if ( !*(_BYTE *)(v288 + 63) )
            {
              for ( jj = *(_QWORD **)(v288 + 72); jj; jj = (_QWORD *)jj[1] )
              {
                fkTriggerDelete(v8, jj[6]);
                jj[6] = 0;
                kk = fkTriggerDelete(v8, jj[7]);
                jj[7] = 0;
              }
            }
          }
        }
        else if ( (_DWORD)kk == 2 )
        {
          kk = v738[12];
          *(_BYTE *)(*(_QWORD *)(v286 + v285 + 24) + 112LL) = kk;
        }
        v20 = v738;
        if ( *((_DWORD *)v738 + 1) == 1 )
        {
          for ( kk = v8[1]; kk; kk = *(_QWORD *)(kk + 16) )
          {
            *(_DWORD *)(kk + 200) &= ~2u;
            *(_DWORD *)(kk + 200) |= 1u;
          }
          *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
        }
        if ( !updated )
          goto LABEL_571;
        goto LABEL_487;
      case 0x65u:
        v290 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        if ( !v290 || *(_DWORD *)(v290 + 68) != *((_DWORD *)v20 + 2) )
          goto LABEL_913;
        v291 = *(_QWORD *)(v290 + 48);
        sqlite3_free(*(_QWORD *)(v291 + 24));
        *(_QWORD *)(v291 + 24) = 0;
        *(_BYTE *)v291 = 1;
        goto LABEL_926;
      case 0x66u:
      case 0x67u:
      case 0x68u:
      case 0x69u:
        v87 = &v9[14 * *((int *)v20 + 1)];
        v88 = &v9[14 * *((int *)v20 + 2)];
        v89 = *((_WORD *)v88 + 10);
        v90 = &v9[14 * *((int *)v738 + 3)];
        if ( ((*((_BYTE *)v87 + 20) | (unsigned __int8)v89) & 1) == 0 )
        {
          if ( (v89 & 0x24) != 0 )
          {
            v91 = *(_QWORD *)v88;
          }
          else if ( (v89 & 8) != 0 )
          {
            _XMM0.m128i_i64[0] = *(_QWORD *)v88;
            if ( *(double *)v88 >= -9.223372036854775e18 )
            {
              if ( *(double *)_XMM0.m128i_i64 <= 9.223372036854775e18 )
                v91 = (unsigned int)(int)*(double *)_XMM0.m128i_i64;
              else
                v91 = 0x7FFFFFFFFFFFFFFFLL;
            }
            else
            {
              v91 = 0x8000000000000000uLL;
            }
          }
          else if ( (v89 & 0x12) != 0 && *((_QWORD *)v88 + 1) )
          {
            v91 = memIntValue(&v9[14 * *((int *)v738 + 2)], v88);
          }
          else
          {
            v91 = 0;
          }
          v92 = *((_WORD *)v87 + 10);
          if ( (v92 & 0x24) != 0 )
          {
            v93 = *(_QWORD *)v87;
          }
          else if ( (v92 & 8) != 0 )
          {
            _XMM0.m128i_i64[0] = *(_QWORD *)v87;
            if ( *(double *)v87 >= -9.223372036854775e18 )
            {
              if ( *(double *)_XMM0.m128i_i64 <= 9.223372036854775e18 )
                v93 = (unsigned int)(int)*(double *)_XMM0.m128i_i64;
              else
                v93 = 0x7FFFFFFFFFFFFFFFLL;
            }
            else
            {
              v93 = 0x8000000000000000uLL;
            }
          }
          else if ( (v92 & 0x12) != 0 && *((_QWORD *)v87 + 1) )
          {
            v93 = memIntValue(v87, v88);
          }
          else
          {
            v93 = 0;
          }
          v94 = *v738;
          if ( *v738 == 102 )
          {
            v95 = v91 & v93;
LABEL_292:
            *(_QWORD *)v90 = v95;
            kk = 62020;
            *((_WORD *)v90 + 10) &= 0xF244u;
            v20 = v738;
            *((_WORD *)v90 + 10) |= 4u;
            goto LABEL_570;
          }
          if ( v94 == 103 )
          {
            v95 = v91 | v93;
            goto LABEL_292;
          }
          v95 = v91;
          if ( !v93 )
            goto LABEL_292;
          if ( v93 < 0 )
          {
            v96 = -47 - v94;
            if ( v93 > -64 )
            {
              v93 = -v93;
LABEL_282:
              if ( v93 < 64 )
              {
                if ( v96 == 104 )
                {
                  v95 = v91 << v93;
                }
                else if ( v91 >= 0 )
                {
                  v95 = (unsigned __int64)v91 >> v93;
                }
                else
                {
                  v95 = ((unsigned __int64)v91 >> v93) | (-1LL << (64 - (unsigned __int8)v93));
                }
                goto LABEL_292;
              }
            }
            if ( v91 >= 0 || v96 == 104 )
              v95 = 0;
            else
              v95 = -1;
            goto LABEL_292;
          }
          v96 = *v738;
          goto LABEL_282;
        }
        kk = 36864;
        if ( (v90[5] & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v738 + 3)], v88);
          v20 = v738;
          goto LABEL_570;
        }
        v13 = 1;
        *((_WORD *)v90 + 10) = 1;
        v10 = v737;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v18 = v751;
        continue;
      case 0x6Au:
      case 0x6Bu:
      case 0x6Cu:
      case 0x6Du:
      case 0x6Eu:
        v72 = &v9[14 * *((int *)v20 + 1)];
        v73 = &v9[14 * *((int *)v20 + 2)];
        v74 = *((unsigned __int16 *)v73 + 10);
        v75 = *((_WORD *)v72 + 10);
        v76 = &v9[14 * *((int *)v20 + 3)];
        if ( ((unsigned __int8)v75 & (unsigned __int8)v74 & 4) != 0 )
          goto LABEL_166;
        LOBYTE(v74) = v75 | v74;
        if ( (v74 & 1) != 0 )
          goto LABEL_237;
        v77 = v72[5] & 0x2D;
        if ( !v77 )
          LOBYTE(v77) = computeNumericType(&v9[14 * *((int *)v20 + 1)]);
        v78 = v73[5] & 0x2D;
        if ( !v78 )
          LOBYTE(v78) = computeNumericType(v73);
        if ( ((unsigned __int8)v77 & (unsigned __int8)v78 & 4) == 0 )
          goto LABEL_208;
LABEL_166:
        v79 = *(_QWORD *)v72;
        v80 = *(_QWORD *)v73;
        switch ( *v738 )
        {
          case 'j':
            if ( v79 < 0 )
            {
              if ( v80 >= 0 || (__int64)(0x8000000000000001uLL - v80) <= v79 + 1 )
              {
LABEL_197:
                v81 = v79 + v80;
                goto LABEL_198;
              }
            }
            else if ( v80 <= 0 || 0x7FFFFFFFFFFFFFFFLL - v80 >= v79 )
            {
              goto LABEL_197;
            }
            break;
          case 'k':
            if ( v79 == 0x8000000000000000uLL )
            {
              if ( v80 < 0 )
              {
                v81 = v80 + 0x8000000000000000uLL;
                goto LABEL_198;
              }
            }
            else
            {
              v79 = -v79;
              if ( v79 < 0 )
              {
                if ( v80 >= 0 || (__int64)(0x8000000000000001uLL - v80) <= v79 + 1 )
                  goto LABEL_197;
              }
              else if ( v80 <= 0 || 0x7FFFFFFFFFFFFFFFLL - v80 >= v79 )
              {
                goto LABEL_197;
              }
            }
            break;
          case 'l':
            if ( v79 <= 0 )
            {
              if ( v79 >= 0 )
                goto LABEL_190;
              if ( v80 <= 0 )
              {
                if ( v80 >= 0
                  || v79 != 0x8000000000000000uLL
                  && v80 != 0x8000000000000000uLL
                  && (v74 = (__int64)0x8000000000000001uLL % v79, -v80 <= (__int64)0x8000000000000001uLL / v79) )
                {
LABEL_190:
                  v81 = v79 * v80;
                  goto LABEL_198;
                }
              }
              else
              {
                v74 = (__int64)0x8000000000000000uLL % v80;
                if ( v79 >= (__int64)0x8000000000000000uLL / v80 )
                {
                  v81 = v79 * v80;
                  goto LABEL_198;
                }
              }
            }
            else
            {
              v74 = 0x7FFFFFFFFFFFFFFFLL % v79;
              if ( v80 <= 0x7FFFFFFFFFFFFFFFLL / v79 )
              {
                v74 = (__int64)0x8000000000000000uLL % v79;
                if ( v80 >= (__int64)0x8000000000000000uLL / v79 )
                {
                  v81 = v79 * v80;
                  goto LABEL_198;
                }
              }
            }
            break;
          case 'm':
            if ( !v79 )
              goto LABEL_236;
            if ( v79 != -1 || v80 != 0x8000000000000000uLL )
            {
              v81 = v80 / v79;
LABEL_198:
              *(_QWORD *)v76 = v81;
              kk = *((unsigned __int16 *)v76 + 10);
              LOWORD(kk) = kk & 0xF240 | 4;
              *((_WORD *)v76 + 10) = kk;
              v7 = a1;
              goto LABEL_569;
            }
            break;
          default:
            if ( v79 )
            {
              if ( v79 == -1 )
                v79 = 1;
              v81 = v80 % v79;
              goto LABEL_198;
            }
            goto LABEL_236;
        }
LABEL_208:
        v82 = *((_WORD *)v72 + 10);
        if ( (v82 & 8) != 0 )
        {
          v83 = *(double *)v72;
        }
        else if ( (v82 & 0x24) != 0 )
        {
          v83 = (double)(int)*(_QWORD *)v72;
        }
        else if ( (v82 & 0x12) != 0 )
        {
          v83 = memRealValue(v72);
        }
        else
        {
          v83 = 0.0;
        }
        v84 = *((_WORD *)v73 + 10);
        if ( (v84 & 8) != 0 )
        {
          _XMM0.m128i_i64[0] = *(_QWORD *)v73;
        }
        else if ( (v84 & 0x24) != 0 )
        {
          *(double *)_XMM0.m128i_i64 = (double)(int)*(_QWORD *)v73;
        }
        else if ( (v84 & 0x12) != 0 )
        {
          *(double *)_XMM0.m128i_i64 = memRealValue(v73);
        }
        else
        {
          _XMM0.m128i_i64[0] = 0;
        }
        switch ( *v738 )
        {
          case 'j':
            *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 + v83;
            break;
          case 'k':
            *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 - v83;
            break;
          case 'l':
            *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 * v83;
            break;
          case 'm':
            if ( v83 == 0.0 )
              goto LABEL_236;
            *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 / v83;
            break;
          default:
            v85 = sqlite3_value_int64(v72);
            v86 = sqlite3_value_int64(v73);
            if ( !v85 )
              goto LABEL_236;
            if ( v85 == -1 )
              v85 = 1;
            *(double *)_XMM0.m128i_i64 = (double)(int)(v86 % v85);
            break;
        }
        v74 = 0x7FF0000000000000LL;
        if ( (_XMM0.m128i_i64[0] & 0xFFFFFFFFFFFFFLL) == 0
          || (_XMM0.m128i_i64[0] & 0x7FF0000000000000LL) != 0x7FF0000000000000LL )
        {
          *(_QWORD *)v76 = _XMM0.m128i_i64[0];
          kk = *((unsigned __int16 *)v76 + 10);
          LOWORD(kk) = kk & 0xF240 | 8;
          *((_WORD *)v76 + 10) = kk;
          v7 = a1;
          goto LABEL_569;
        }
LABEL_236:
        v17 = HIDWORD(v739);
LABEL_237:
        kk = 36864;
        if ( (v76[5] & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(v76, v74);
          v7 = a1;
          goto LABEL_569;
        }
        v12 = 0x180000000uLL;
        v10 = v737;
        v13 = 1;
        v5 = v741;
        *((_WORD *)v76 + 10) = 1;
        v7 = a1;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x6Fu:
        v65 = &v9[14 * *((int *)v20 + 1)];
        v66 = &v746[14 * *((int *)v20 + 2)];
        v67 = *((_WORD *)v65 + 10);
        v68 = &v746[14 * *((int *)v20 + 3)];
        if ( ((*((_BYTE *)v66 + 20) | (unsigned __int8)v67) & 1) == 0 )
        {
          if ( (v67 & 0x12) == 0 )
          {
            if ( !(unsigned int)sqlite3VdbeMemStringify(v65, v10, 0) )
            {
              v67 = v65[5] & 0xFFFD;
              goto LABEL_146;
            }
LABEL_1991:
            v154 = (_QWORD *)v742;
LABEL_581:
            v11 = v743;
LABEL_582:
            sqlite3OomFault(v154);
            sqlite3VdbeError(v7, "out of memory");
            updated = 7;
            goto LABEL_489;
          }
          if ( (v67 & 0x400) != 0 )
          {
            if ( (unsigned int)sqlite3VdbeMemExpandBlob(v65, 1) )
              goto LABEL_1991;
            v67 = v65[5] & 0xFFFD;
          }
LABEL_146:
          v69 = *((_WORD *)v66 + 10);
          if ( (v69 & 0x12) == 0 )
          {
            v70 = sqlite3VdbeMemStringify(v66, v737, 0);
            goto LABEL_150;
          }
          if ( (v69 & 0x400) != 0 )
          {
            v70 = sqlite3VdbeMemExpandBlob(v66, v13);
LABEL_150:
            if ( v70 )
              goto LABEL_1991;
            v69 = v66[5] & 0xFFFD;
          }
          LODWORD(v71) = v65[4] + v66[4];
          if ( (int)v71 <= *((_DWORD *)v8 + 34) )
          {
            if ( !(unsigned int)sqlite3VdbeMemGrow(v68, (unsigned int)(v71 + 2), v68 == v66) )
            {
              v71 = (int)v71;
              *((_WORD *)v68 + 10) &= 0xF242u;
              *((_WORD *)v68 + 10) |= 2u;
              if ( v68 != v66 )
              {
                memcpy_0(*((void **)v68 + 1), *((const void **)v66 + 1), (int)v66[4]);
                *((_WORD *)v66 + 10) = v69;
              }
              memcpy_0((void *)(*((_QWORD *)v68 + 1) + (int)v66[4]), *((const void **)v65 + 1), (int)v65[4]);
              v10 = v737;
              *((_WORD *)v65 + 10) = v67;
              if ( v737 > 1u )
                v71 = (int)v71 & 0xFFFFFFFFFFFFFFFEuLL;
              updated = v739;
              v20 = v738;
              v9 = v746;
              *(_BYTE *)(v71 + *((_QWORD *)v68 + 1)) = 0;
              *(_BYTE *)(*((_QWORD *)v68 + 1) + v71 + 1) = 0;
              kk = 512;
              *((_WORD *)v68 + 10) |= 0x200u;
              v68[4] = v71;
              v7 = a1;
              *((_BYTE *)v68 + 22) = v737;
              goto LABEL_571;
            }
LABEL_579:
            v154 = (_QWORD *)v742;
LABEL_580:
            v7 = a1;
            goto LABEL_581;
          }
LABEL_1983:
          v154 = (_QWORD *)v742;
LABEL_1984:
          v7 = a1;
LABEL_1985:
          sqlite3VdbeError(v7, "string or blob too big");
          updated = 18;
          goto LABEL_488;
        }
        kk = 36864;
        if ( (v68[5] & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(&v746[14 * *((int *)v20 + 3)], 1);
          v20 = v738;
          updated = v739;
          v9 = v746;
          goto LABEL_571;
        }
        updated = v739;
        v13 = 1;
        v9 = v746;
        *((_WORD *)v68 + 10) = 1;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x70u:
      case 0x71u:
LABEL_913:
        if ( (v7[25] & 3) == 1 )
        {
          updated = 516;
          goto LABEL_487;
        }
        v292 = v8[4];
        v293 = *((_DWORD *)v738 + 3);
        v294 = *((unsigned int *)v738 + 2);
        v295 = 32LL * v293;
        v296 = *(_QWORD *)(v295 + v292 + 8);
        if ( (_BYTE)v21 == 113 )
        {
          v13 = (unsigned __int64)v738;
          v297 = *(_BYTE *)(*(_QWORD *)(v295 + v292 + 24) + 112LL);
          v298 = *((_WORD *)v738 + 1) & 8 | 4;
          if ( v297 < *((_BYTE *)a1 + 197) )
            *((_BYTE *)a1 + 197) = v297;
        }
        else
        {
          v298 = 0;
        }
        v299 = v738;
        if ( (v738[2] & 0x10) != 0 )
        {
          sqlite3VdbeMemIntegerify(&v746[14 * v294], v13);
          v299 = v738;
          LODWORD(v294) = v746[14 * v294];
        }
        v300 = v299[1];
        if ( v300 == 0xF8 )
        {
          v301 = *((_QWORD *)v299 + 2);
          v302 = *(unsigned __int16 *)(v301 + 8);
        }
        else
        {
          v302 = 0;
          v301 = 0;
          if ( v300 == 0xFD )
            v302 = *((unsigned int *)v299 + 4);
        }
        Cursor = allocateCursor(a1, *((unsigned int *)v299 + 1), v302, 0);
        v290 = Cursor;
        if ( !Cursor )
          goto LABEL_579;
        *(_BYTE *)(Cursor + 1) = v293;
        *(_BYTE *)(Cursor + 2) = 1;
        *(_DWORD *)(Cursor + 8) |= 4u;
        *(_DWORD *)(Cursor + 68) = v294;
        v304 = sqlite3BtreeCursor(v296, v294, v298, v301, *(_QWORD *)(Cursor + 48));
        v7 = a1;
        updated = v304;
        v9 = v746;
        LODWORD(v739) = v304;
        *(_QWORD *)(v290 + 56) = v301;
        *(_BYTE *)(v290 + 4) = v738[1] != 0xF8;
LABEL_926:
        kk = *(_QWORD *)(v290 + 48);
        *(_BYTE *)(kk + 3) = v738[2] & 3;
        if ( updated )
          goto LABEL_487;
        goto LABEL_569;
      case 0x72u:
        v133 = &v9[14 * *((int *)v20 + 1)];
        kk = 36864;
        v134 = &v9[14 * *((int *)v20 + 2)];
        if ( (v134[5] & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v20 + 2)], 1);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v13 = 1;
        }
        else
        {
          *((_WORD *)v134 + 10) = 1;
        }
        if ( (v133[5] & 1) != 0 )
          goto LABEL_70;
        *((_WORD *)v134 + 10) = 4;
        v135 = sqlite3_value_int64(v133);
        v20 = v738;
        kk = ~v135;
        *(_QWORD *)v134 = kk;
        goto LABEL_571;
      case 0x73u:
        v305 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 2));
        v306 = allocateCursor(v7, *((unsigned int *)v20 + 1), (unsigned int)*(__int16 *)(v305 + 72), 0);
        if ( !v306 )
          goto LABEL_1991;
        *(_BYTE *)(v306 + 2) = 1;
        *(_DWORD *)(v306 + 8) |= 1u;
        *(_QWORD *)(v306 + 56) = *(_QWORD *)(v305 + 56);
        *(_BYTE *)(v306 + 4) = *(_BYTE *)(v305 + 4);
        *(_DWORD *)(v306 + 68) = *(_DWORD *)(v305 + 68);
        v307 = *(_DWORD *)(v306 + 8) ^ (*(_DWORD *)(v305 + 8) ^ *(_DWORD *)(v306 + 8)) & 4;
        *(_DWORD *)(v306 + 8) = v307;
        *(_QWORD *)(v306 + 16) = *(_QWORD *)(v305 + 16);
        *(_DWORD *)(v306 + 8) = v307 | 8;
        *(_DWORD *)(v305 + 8) |= 8u;
        kk = sqlite3BtreeCursor(
               *(_QWORD *)(v306 + 16),
               *(_DWORD *)(v306 + 68),
               4,
               *(_QWORD *)(v306 + 56),
               *(_QWORD *)(v306 + 48));
        v20 = v738;
        updated = kk;
        LODWORD(v739) = kk;
        goto LABEL_571;
      case 0x74u:
      case 0x76u:
        v308 = *((int *)v20 + 3);
        if ( (int)v308 > 0 )
        {
          v9[14 * v308 + 4] = 0;
          *(_QWORD *)&v9[14 * *((int *)v20 + 3) + 2] = byte_180122168;
        }
        v309 = *((int *)v20 + 1);
        v310 = *(_QWORD *)(v7[15] + 8 * v309);
        if ( v310 && (*(_BYTE *)(v310 + 8) & 8) == 0 && *((_DWORD *)v20 + 2) <= *(__int16 *)(v310 + 72) )
        {
          *(_QWORD *)(v310 + 24) = 0;
          *(_DWORD *)(v310 + 32) = 0;
          kk = sqlite3BtreeClearTable(*(_QWORD *)(v310 + 16), *(unsigned int *)(v310 + 68), 0);
          LODWORD(v739) = kk;
          updated = kk;
          if ( (_DWORD)kk )
            goto LABEL_487;
          v20 = v738;
          *(_BYTE *)(v310 + 2) = 1;
          goto LABEL_571;
        }
        v311 = allocateCursor(v7, v309, *((unsigned int *)v20 + 2), 0);
        v312 = v311;
        if ( v311 )
        {
          *(_DWORD *)(v311 + 8) |= 1u;
          LODWORD(v736) = *((unsigned __int16 *)v738 + 1) | 5;
          updated = sqlite3BtreeOpen(*v8, 0, v8, v311 + 16, v736, 1054);
          if ( updated )
            goto LABEL_487;
          v313 = *(_QWORD *)(v312 + 16);
          if ( *(_BYTE *)(v313 + 17) || *(_BYTE *)(v313 + 16) < 2u )
          {
            updated = btreeBeginTrans(v313, 1, 0);
            LODWORD(v739) = updated;
          }
          else
          {
            v314 = *(_QWORD *)(v313 + 8);
            if ( *(_DWORD *)(*(_QWORD *)v313 + 752LL) <= *(_DWORD *)(*(_QWORD *)v314 + 128LL)
              || *(_BYTE *)(*(_QWORD *)v314 + 10LL) == (_BYTE)updated )
            {
              updated = 0;
              LODWORD(v739) = 0;
            }
            else
            {
              updated = ((__int64 (*)(void))pagerOpenSavepoint)();
              LODWORD(v739) = updated;
            }
          }
          if ( !updated )
          {
            v315 = *((_QWORD *)v738 + 2);
            *(_QWORD *)(v312 + 56) = v315;
            if ( v315 )
            {
              LODWORD(v739) = sqlite3BtreeCreateTable(
                                *(_QWORD *)(v312 + 16),
                                v312 + 68,
                                *((unsigned __int16 *)v738 + 1) | 2u);
              updated = v739;
              if ( !(_DWORD)v739 )
              {
                updated = sqlite3BtreeCursor(
                            *(_QWORD *)(v312 + 16),
                            *(_DWORD *)(v312 + 68),
                            4,
                            v315,
                            *(_QWORD *)(v312 + 48));
                LODWORD(v739) = updated;
              }
              *(_BYTE *)(v312 + 4) = 0;
            }
            else
            {
              *(_DWORD *)(v312 + 68) = 1;
              updated = sqlite3BtreeCursor(*(_QWORD *)(v312 + 16), 1, 4, 0, *(_QWORD *)(v312 + 48));
              LODWORD(v739) = updated;
              *(_BYTE *)(v312 + 4) = 1;
            }
            v10 = v737;
          }
          v316 = 0;
          if ( *((_WORD *)v738 + 1) != 8 )
            v316 = 4;
          kk = *(_DWORD *)(v312 + 8) & 0xFFFFFFFB;
          *(_DWORD *)(v312 + 8) = kk | v316;
          if ( updated )
          {
            sqlite3BtreeClose(*(_QWORD *)(v312 + 16));
            goto LABEL_487;
          }
          v20 = v738;
          *(_BYTE *)(v312 + 2) = 1;
          goto LABEL_571;
        }
        goto LABEL_1991;
      case 0x75u:
        v36 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v36 + 20) & 0x9000) != 0 )
          v36 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
        else
          *(_WORD *)(v36 + 20) = 4;
        v20 = v738;
        v37 = *((_QWORD *)v738 + 2);
        if ( v37 )
        {
          v39 = strlen_0(*((const char **)v738 + 2));
          v20 = v738;
          v38 = v39 & 0x3FFFFFFF;
        }
        else
        {
          v38 = 0;
        }
        *((_DWORD *)v20 + 1) = v38;
        if ( v10 == 1 )
          goto LABEL_52;
        LOBYTE(v6) = 1;
        LODWORD(v739) = sqlite3VdbeMemSetStr(v36, v37, -1, v6, 0);
        updated = v739;
        if ( (_DWORD)v739 )
          goto LABEL_1986;
        if ( (*(_BYTE *)(v36 + 20) & 2) != 0 )
        {
          if ( *(_BYTE *)(v36 + 22) != v10 && (unsigned int)sqlite3VdbeMemTranslate(v36, v10) )
            goto LABEL_1991;
        }
        else
        {
          *(_BYTE *)(v36 + 22) = v10;
        }
        v20 = v738;
        *(_DWORD *)(v36 + 32) = 0;
        *(_WORD *)(v36 + 20) |= 0x2000u;
        if ( v738[1] == 0xFA )
        {
          v40 = *((_QWORD *)v738 + 2);
          if ( v40 )
          {
            sqlite3DbFreeNN(v8, v40);
            v20 = v738;
          }
        }
        v20[1] = -6;
        *((_QWORD *)v20 + 2) = *(_QWORD *)(v36 + 8);
        v38 = *(_DWORD *)(v36 + 16);
        *((_DWORD *)v20 + 1) = v38;
LABEL_52:
        if ( v38 > *((_DWORD *)v8 + 34) )
        {
LABEL_1986:
          v154 = (_QWORD *)v742;
          goto LABEL_1985;
        }
        *v20 = 73;
LABEL_54:
        v41 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v41 + 20) & 0x9000) != 0 )
          v41 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v41);
        v20 = v738;
        *(_WORD *)(v41 + 20) = 8706;
        *(_QWORD *)(v41 + 8) = *((_QWORD *)v738 + 2);
        *(_DWORD *)(v41 + 16) = *((_DWORD *)v738 + 1);
        *(_BYTE *)(v41 + 22) = v10;
        kk = *((int *)v738 + 3);
        if ( (int)kk > 0 )
        {
          v42 = 14 * kk;
          kk = *((unsigned __int16 *)v738 + 1);
          v195 = *(_QWORD *)&v9[v42] == kk;
          v20 = v738;
          if ( v195 )
          {
            *(_WORD *)(v41 + 20) = 8720;
            goto LABEL_571;
          }
        }
        v13 = 1;
        goto LABEL_107;
      case 0x77u:
        LOBYTE(v6) = 1;
        v317 = allocateCursor(v7, *((unsigned int *)v20 + 1), *((unsigned int *)v20 + 2), v6);
        if ( !v317 )
          goto LABEL_1991;
        *(_QWORD *)(v317 + 56) = *((_QWORD *)v738 + 2);
        kk = sqlite3VdbeSorterInit(v8, *((unsigned int *)v738 + 3), v317);
        goto LABEL_959;
      case 0x78u:
        v319 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v320 = *(_QWORD *)(v319 + 24);
        kk = v320 + 1;
        *(_QWORD *)(v319 + 24) = v320 + 1;
        if ( !v320 )
          goto LABEL_1258;
        v20 = v738;
        goto LABEL_574;
      case 0x79u:
        LOBYTE(v6) = 3;
        kk = allocateCursor(v7, *((unsigned int *)v20 + 1), *((unsigned int *)v20 + 3), v6);
        if ( !kk )
          goto LABEL_1991;
        *(_BYTE *)(kk + 2) = 1;
        *(_DWORD *)(kk + 36) = *((_DWORD *)v738 + 2);
        *(_BYTE *)(kk + 4) = 1;
        *(_QWORD *)(kk + 48) = &dword_18013FAD4;
        v20 = v738;
        goto LABEL_571;
      case 0x7Au:
        if ( *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) )
        {
          sqlite3VdbeFreeCursorNN(v7);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
        }
        kk = v7[15];
        *(_QWORD *)(kk + 8LL * *((int *)v738 + 1)) = 0;
        v20 = v738;
        goto LABEL_574;
      case 0x7Cu:
        v337 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 7));
        kk = *(_QWORD *)(v337 + 48);
        if ( *(_BYTE *)kk )
        {
LABEL_90:
          v20 = v738;
LABEL_91:
          v10 = v737;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v6 = v744;
          v18 = v751;
          continue;
        }
        v338 = v20;
        v816[0] = *(_QWORD *)(v337 + 56);
        v818 = 0;
        v339 = *((_DWORD *)v20 + 1);
        v817 = *((_WORD *)v20 + 20);
        v816[1] = &v9[14 * *((int *)v20 + 9)];
        while ( 2 )
        {
          v340 = *(_QWORD *)(v337 + 48);
          getCellInfo(v340);
          v341 = *(_DWORD *)(v340 + 64);
          if ( v341 - 1 > 0x7FFFFFFE )
          {
            v723 = 88912;
LABEL_1980:
            sqlite3_log(
              11,
              "%s at line %d of [%.10s]",
              "database corruption",
              v723,
              "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
            updated = 11;
LABEL_1967:
            v154 = (_QWORD *)v742;
            goto LABEL_488;
          }
          v788 = v8;
          v787 = 0;
          v789 = 0;
          v342 = *(_DWORD *)(*(_QWORD *)(v340 + 136) + 88LL) - *(_DWORD *)(v340 + 56);
          if ( *(unsigned __int16 *)(v340 + 68) <= v342 )
          {
            v342 = *(unsigned __int16 *)(v340 + 68);
          }
          else if ( v342 < 0 )
          {
            v342 = 0;
          }
          v343 = *(_QWORD *)(v340 + 56);
          v785 = v343;
          if ( v341 > v342 )
          {
            updated = sqlite3VdbeMemFromBtree(v340, 0, v341, v784);
            if ( updated )
              goto LABEL_487;
            v341 = v786;
            v343 = v785;
            v338 = v738;
          }
          else
          {
            v786 = v341;
            v787 = 16400;
          }
          kk = sqlite3VdbeRecordCompareWithSkip(v341, v343, v816, 0);
          v345 = kk;
          if ( v789 )
            kk = vdbeMemClear(v784);
          v346 = v345 < 0;
          if ( v345 > 0 )
          {
            if ( !*((_WORD *)v338 + 1) )
              goto LABEL_1056;
            v346 = v345 < 0;
          }
          if ( !v346 )
            goto LABEL_1695;
          if ( v339 <= 0 )
          {
            updated = 0;
            LODWORD(v739) = 0;
            goto LABEL_569;
          }
          *(_DWORD *)(v337 + 32) = 0;
          v347 = *(_QWORD *)(v337 + 48);
          *(_WORD *)(v347 + 70) = 0;
          *(_BYTE *)(v347 + 1) &= 0xF9u;
          if ( *(_BYTE *)v347 )
          {
            v348 = btreeNext(v347, v344);
          }
          else
          {
            v349 = *(_WORD *)(v347 + 86);
            v350 = *(_QWORD *)(v347 + 136);
            *(_WORD *)(v347 + 86) = v349 + 1;
            if ( (unsigned __int16)(v349 + 1) < *(_WORD *)(v350 + 24) )
            {
              if ( *(_BYTE *)(v350 + 8) )
                goto LABEL_1054;
              v348 = moveToLeftmost(v347);
            }
            else
            {
              *(_WORD *)(v347 + 86) = v349;
              v348 = btreeNext(v347, v350);
            }
          }
          updated = v348;
          if ( !v348 )
          {
LABEL_1054:
            v338 = v738;
            --v339;
            continue;
          }
          break;
        }
        if ( v348 != 101 )
          goto LABEL_487;
LABEL_1056:
        updated = 0;
        LODWORD(v739) = 0;
        v5 = v741;
        v20 = v738 + 24;
LABEL_1259:
        v13 = 1;
LABEL_1260:
        v7 = a1;
        v9 = v746;
        v10 = v737;
        kk = *((_DWORD *)v20 + 2) - 1;
        v20 = &v5[24 * (int)kk];
LABEL_108:
        v17 = HIDWORD(v739);
        v12 = 0x180000000uLL;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x7Du:
        v351 = *((_DWORD *)v20 + 2);
        kk = v7[15];
        v352 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        v353 = *(unsigned __int16 *)(v352 + 12);
        if ( v353 < v351 )
        {
          v20 = v738;
          *(_WORD *)(v352 + 12) = v351;
          goto LABEL_573;
        }
        v17 = HIDWORD(v739);
        kk = *((unsigned int *)v738 + 3);
        v354 = v353 <= (int)kk;
        v20 = v738;
        if ( !v354 )
          *(_WORD *)(v352 + 12) = kk;
        goto LABEL_574;
      case 0x7Eu:
        v367 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v367 + 20) & 0x9000) != 0 )
        {
          v368 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v367);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v367 = v368;
        }
        else
        {
          *(_WORD *)(v367 + 20) = 4;
        }
        *(_QWORD *)v367 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v738 + 1)) + 24LL);
        kk = v7[15];
        v369 = *(_QWORD *)(kk + 8LL * *((int *)v738 + 1));
        v20 = v738;
        ++*(_QWORD *)(v369 + 24);
        goto LABEL_574;
      case 0x7Fu:
        v370 = 0;
        v371 = v7[13];
        v372 = 0;
        v747 = 0;
        v749 = 0;
        v373 = 56LL * *((int *)v20 + 2) + v371;
        if ( (*(_WORD *)(v373 + 20) & 0x9000) != 0 )
          v373 = out2PrereleaseWithClear(v373, 1);
        else
          *(_WORD *)(v373 + 20) = 4;
        v374 = *(_QWORD *)(a1[15] + 8LL * *((int *)v738 + 1));
        if ( (*(_BYTE *)(v374 + 8) & 2) != 0 )
          goto LABEL_1114;
        v375 = *(_BYTE **)(v374 + 48);
        if ( *v375 || (v375[1] & 8) == 0 )
        {
          LODWORD(v739) = btreeLast(v375, &v749);
          updated = v739;
          if ( (_DWORD)v739 )
            goto LABEL_1134;
          v372 = v749;
        }
        else
        {
          updated = 0;
          LODWORD(v739) = 0;
        }
        if ( v372 )
        {
          v370 = 1;
          v747 = 1;
        }
        else
        {
          v378 = *(_QWORD *)(v374 + 48);
          getCellInfo(v378);
          v370 = *(_QWORD *)(v378 + 48);
          v747 = v370;
          if ( v370 == 0x7FFFFFFFFFFFFFFFLL )
            *(_DWORD *)(v374 + 8) |= 2u;
          else
            v747 = ++v370;
        }
LABEL_1114:
        kk = *((int *)v738 + 3);
        if ( (_DWORD)kk )
        {
          v376 = a1[33];
          if ( v376 )
          {
            for ( ; *(_QWORD *)(v376 + 8); v376 = *(_QWORD *)(v376 + 8) )
              ;
            v377 = (__int64 *)(*(_QWORD *)(v376 + 24) + 56LL * *((int *)v738 + 3));
          }
          else
          {
            v377 = (__int64 *)&v746[14 * kk];
          }
          sqlite3VdbeMemIntegerify(v377, v738);
          if ( *v377 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v374 + 8) & 2) != 0 )
          {
LABEL_1133:
            updated = 13;
            goto LABEL_1134;
          }
          kk = *v377 + 1;
          if ( v370 < kk )
            v370 = *v377 + 1;
          v747 = v370;
          *v377 = v370;
        }
        if ( (*(_BYTE *)(v374 + 8) & 2) == 0 )
        {
LABEL_1135:
          *(_BYTE *)(v374 + 3) = 0;
          *(_DWORD *)(v374 + 32) = 0;
          *(_QWORD *)v373 = v370;
          v7 = a1;
          goto LABEL_568;
        }
        v379 = 0;
        while ( 1 )
        {
          sqlite3_randomness(8, &v747);
          v380 = *(_QWORD *)(v374 + 48);
          v370 = (v747 & 0x3FFFFFFFFFFFFFFFLL) + 1;
          v747 = v370;
          kk = sqlite3BtreeTableMoveto(v380, v370, 0, &v749);
          LODWORD(v739) = kk;
          updated = kk;
          if ( (_DWORD)kk )
            break;
          if ( v749 )
            goto LABEL_1135;
          if ( ++v379 >= 100 )
            goto LABEL_1133;
        }
LABEL_1134:
        v7 = a1;
        goto LABEL_487;
      case 0x80u:
        v381 = 14LL * *((int *)v20 + 2);
        v382 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v797 = *(_QWORD *)&v9[14 * *((int *)v20 + 3)];
        if ( v20[1] == 0xFB && v8[40] )
        {
          v383 = (_QWORD *)*((_QWORD *)v20 + 2);
          v384 = *(_QWORD *)(32LL * *(char *)(v382 + 1) + v8[4]);
        }
        else
        {
          v383 = 0;
          v384 = 0;
        }
        if ( (v20[2] & 1) != 0 )
        {
          ++v7[7];
          if ( (v20[2] & 0x20) != 0 )
            v8[7] = v797;
        }
        v798 = *(_QWORD *)&v9[v381 + 2];
        v799 = v9[v381 + 4];
        if ( (v20[2] & 0x10) != 0 )
          v385 = *(unsigned int *)(v382 + 36);
        else
          v385 = 0;
        if ( (v9[v381 + 5] & 0x400) != 0 )
          v800 = v9[v381];
        else
          v800 = 0;
        v796 = 0;
        kk = sqlite3BtreeInsert(*(_QWORD *)(v382 + 48), &v796, *((_WORD *)v20 + 1) & 0x8A, v385);
        *(_BYTE *)(v382 + 3) = 0;
        updated = kk;
        LODWORD(v739) = kk;
        *(_DWORD *)(v382 + 32) = 0;
        if ( (_DWORD)kk )
          goto LABEL_487;
        ++v751;
        if ( v383 )
        {
          v386 = 18;
          if ( (v738[2] & 4) != 0 )
            v386 = 23;
          kk = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64))v8[40])(
                 v8[39],
                 v386,
                 v384,
                 *v383,
                 v797);
        }
        goto LABEL_569;
      case 0x81u:
        v387 = v7[15];
        v388 = *(_QWORD *)(v387 + 8LL * *((int *)v738 + 1));
        v389 = *(_QWORD *)(v387 + 8LL * *((int *)v738 + 2));
        v390 = *((int *)v738 + 3);
        if ( (_DWORD)v390 )
          kk = sqlite3BtreeTransferRow(*(_QWORD *)(v388 + 48), *(_QWORD *)(v389 + 48), *(_QWORD *)&v9[14 * v390]);
        else
          kk = sqlite3BtreeTransferRow(*(_QWORD *)(v388 + 48), *(_QWORD *)(v389 + 48), 0);
        goto LABEL_959;
      case 0x82u:
        v391 = *((_DWORD *)v20 + 2);
        v392 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        if ( v20[1] == 0xFB && v8[40] )
        {
          v393 = *((_QWORD *)v20 + 2);
          v394 = *(_QWORD *)(32LL * *(char *)(v392 + 1) + v8[4]);
          if ( (v20[2] & 2) != 0 && *(_BYTE *)(v392 + 4) )
          {
            v395 = *(_QWORD *)(v392 + 48);
            getCellInfo(v395);
            v396 = *(_QWORD *)(v395 + 48);
            v18 = v751;
            *(_QWORD *)(v392 + 80) = v396;
          }
        }
        else
        {
          v394 = 0;
          v393 = 0;
        }
        kk = sqlite3BtreeDelete(*(_QWORD *)(v392 + 48), v738[2]);
        *(_DWORD *)(v392 + 32) = 0;
        updated = kk;
        LODWORD(v739) = kk;
        *(_DWORD *)(v392 + 36) = 0;
        if ( (_DWORD)kk )
          goto LABEL_486;
        v751 = v18 + 1;
        if ( (v391 & 1) != 0 )
        {
          ++a1[7];
          kk = v8[40];
          if ( kk )
          {
            if ( v393 && *(char *)(v393 + 48) >= 0 )
              kk = ((__int64 (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))kk)(
                     v8[39],
                     9,
                     v394,
                     *(_QWORD *)v393,
                     *(_QWORD *)(v392 + 80));
          }
        }
        goto LABEL_567;
      case 0x83u:
        kk = v7[7];
        v8[15] = kk;
        v8[16] += kk;
        v7[7] = 0;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0x84u:
        v397 = *((int *)v20 + 3);
        v398 = *((_DWORD *)v20 + 4);
        v399 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v400 = *(_QWORD *)(v399 + 48);
        v401 = *(_QWORD *)(v399 + 56);
        v402 = *(_QWORD *)(v400 + 48);
        if ( v402 )
          goto LABEL_1173;
        v403 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v399 + 56));
        *(_QWORD *)(v400 + 48) = v403;
        v402 = v403;
        if ( !v403 )
        {
          updated = 7;
          goto LABEL_486;
        }
        *(_WORD *)(v403 + 28) = v398;
LABEL_1173:
        if ( *(_BYTE *)(v400 + 88) )
        {
          if ( *(_BYTE *)(v400 + 89) )
            v404 = *(_QWORD *)(v400 + 16);
          else
            v404 = *(_QWORD *)(*(_QWORD *)(v400 + 24) + 24LL)
                 + 80LL * *(int *)(*(_QWORD *)(*(_QWORD *)(v400 + 24) + 16LL) + 4LL);
          v405 = *(unsigned int **)(v404 + 40);
          v406 = (unsigned int *)(v404 + 20);
        }
        else
        {
          v406 = *(unsigned int **)(v400 + 56);
          v405 = v406 + 4;
        }
        sqlite3VdbeRecordUnpack(v401, *v406, v405, v402);
        if ( v398 <= 0 )
          goto LABEL_1183;
        for ( mm = 0; mm < v398; ++mm )
        {
          if ( (*(_BYTE *)(56LL * (unsigned int)mm + *(_QWORD *)(v402 + 8) + 20) & 1) != 0 )
          {
LABEL_1695:
            updated = 0;
LABEL_1256:
            LODWORD(v739) = updated;
            goto LABEL_1257;
          }
        }
LABEL_1183:
        v408 = 14 * v397;
        v9 = v746;
        kk = sqlite3VdbeRecordCompareWithSkip((unsigned int)v746[v408 + 4], *(_QWORD *)&v746[v408 + 2], v402, 0);
        updated = 0;
        LODWORD(v739) = 0;
        if ( (_DWORD)kk )
        {
LABEL_1257:
          v5 = v741;
LABEL_1258:
          v20 = v738;
          goto LABEL_1259;
        }
LABEL_1389:
        v7 = a1;
        goto LABEL_569;
      case 0x85u:
        v409 = &v9[14 * *((int *)v20 + 2)];
        v410 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 48LL);
        if ( *(_BYTE *)(v410 + 88) )
        {
          if ( *(_BYTE *)(v410 + 89) )
            v411 = *(_QWORD *)(v410 + 16);
          else
            v411 = *(_QWORD *)(*(_QWORD *)(v410 + 24) + 24LL)
                 + 80LL * *(int *)(*(_QWORD *)(*(_QWORD *)(v410 + 24) + 16LL) + 4LL);
          v412 = *(const void **)(v411 + 40);
          v413 = (int *)(v411 + 20);
        }
        else
        {
          v413 = *(int **)(v410 + 56);
          v412 = v413 + 4;
        }
        v414 = *v413;
        if ( v409[8] >= (int)v414 )
        {
          *((_QWORD *)v409 + 1) = *((_QWORD *)v409 + 5);
          *((_WORD *)v409 + 10) &= 0x2Du;
        }
        else if ( (unsigned int)sqlite3VdbeMemGrow(&v9[14 * *((int *)v20 + 2)], (unsigned int)v414, 0) )
        {
          updated = 7;
          goto LABEL_487;
        }
        v409[4] = v414;
        *((_WORD *)v409 + 10) &= 0xF250u;
        *((_WORD *)v409 + 10) |= 0x10u;
        memcpy_0(*((void **)v409 + 1), v412, v414);
        updated = 0;
        LODWORD(v739) = 0;
        kk = v7[15];
        *(_DWORD *)(*(_QWORD *)(kk + 8LL * *((int *)v738 + 3)) + 32LL) = 0;
        goto LABEL_569;
      case 0x86u:
        v415 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v415 + 20) & 0x9000) != 0 )
          v415 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
        else
          *(_WORD *)(v415 + 20) = 4;
        v416 = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v738 + 1)) + 48LL);
        getCellInfo(v416);
        v417 = *(unsigned int *)(v416 + 64);
        if ( (unsigned int)v417 > *((_DWORD *)v8 + 34) )
          goto LABEL_1986;
        kk = sqlite3VdbeMemFromBtreeZeroOffset(v416, v417, v415);
        LODWORD(v739) = kk;
        updated = kk;
        if ( (_DWORD)kk )
          goto LABEL_487;
        v20 = v738;
        if ( *((_DWORD *)v738 + 3) )
          goto LABEL_571;
        kk = *(unsigned __int16 *)(v415 + 20);
        if ( (kk & 0x4000) == 0 )
          goto LABEL_571;
        if ( (kk & 0x12) != 0 )
        {
          if ( (kk & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v415, v418) )
            goto LABEL_1991;
          if ( !*(_DWORD *)(v415 + 32) || (kk = *(_QWORD *)(v415 + 40), *(_QWORD *)(v415 + 8) != kk) )
          {
            kk = vdbeMemAddTerminator(v415);
            if ( (_DWORD)kk )
              goto LABEL_1991;
          }
        }
        *(_WORD *)(v415 + 20) &= ~0x4000u;
        v20 = v738;
        goto LABEL_571;
      case 0x87u:
        v419 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v419 + 20) & 0x9000) != 0 )
        {
          v420 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v419 = v420;
          v13 = 1;
        }
        else
        {
          *(_WORD *)(v419 + 20) = 4;
        }
        kk = v7[15];
        v421 = *(_QWORD *)(kk + 8LL * *((int *)v738 + 1));
        if ( *(_BYTE *)(v421 + 2) )
        {
          *(_WORD *)(v419 + 20) = 1;
          v8 = (_QWORD *)v742;
          v20 = v738 + 24;
          v6 = v744;
          v18 = v751;
          continue;
        }
        if ( *(_BYTE *)(v421 + 3) )
        {
          kk = *(_QWORD *)(v421 + 80);
          v20 = v738;
          v761 = kk;
          *(_QWORD *)v419 = kk;
          goto LABEL_571;
        }
        v422 = *(__int64 **)(v421 + 48);
        if ( *(_BYTE *)v421 == 2 )
        {
          v423 = *v422;
          LODWORD(v739) = (*(__int64 (__fastcall **)(__int64 *, __int64 *, __int64))(*(_QWORD *)*v422 + 96LL))(
                            v422,
                            &v761,
                            v17);
          updated = v739;
          sqlite3VtabImportErrmsg(v7, v423);
          if ( (_DWORD)v739 )
            goto LABEL_487;
          kk = v761;
          v20 = v738;
          *(_QWORD *)v419 = v761;
          goto LABEL_571;
        }
        if ( *(_BYTE *)v422 )
        {
          kk = sqlite3VdbeHandleMovedCursor(v421, 1);
          LODWORD(v739) = kk;
          updated = kk;
          if ( (_DWORD)kk )
            goto LABEL_487;
        }
        else
        {
          updated = 0;
          LODWORD(v739) = 0;
        }
        if ( !*(_BYTE *)(v421 + 2) )
        {
          v424 = *(_QWORD *)(v421 + 48);
          getCellInfo(v424);
          kk = *(_QWORD *)(v424 + 48);
          v20 = v738;
          v761 = kk;
          *(_QWORD *)v419 = kk;
          goto LABEL_571;
        }
        v13 = 1;
        *(_WORD *)(v419 + 20) = 1;
LABEL_1226:
        v20 = v738;
        goto LABEL_107;
      case 0x88u:
        v425 = *((int *)v20 + 1);
        kk = *(_QWORD *)(v7[15] + 8 * v425);
        if ( kk )
          goto LABEL_1231;
        LOBYTE(v6) = 3;
        kk = allocateCursor(v7, v425, 1, v6);
        if ( !kk )
          goto LABEL_1991;
        *(_DWORD *)(kk + 36) = 0;
        *(_BYTE *)(kk + 4) = 1;
        *(_DWORD *)(kk + 8) |= 8u;
        *(_QWORD *)(kk + 48) = &dword_18013FAD4;
LABEL_1231:
        *(_BYTE *)(kk + 2) = 1;
        *(_DWORD *)(kk + 32) = 0;
        if ( *(_BYTE *)kk )
          goto LABEL_894;
        v426 = *(_QWORD *)(kk + 48);
        kk = sqlite3_free(*(_QWORD *)(v426 + 24));
        v20 = v738;
        *(_QWORD *)(v426 + 24) = 0;
        *(_BYTE *)v426 = 1;
        goto LABEL_571;
      case 0x8Au:
        v449 = v20;
        v450 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v451 = &v9[14 * *((int *)v20 + 2)];
        if ( (v20[2] & 1) != 0 )
          ++v7[7];
        if ( (v451[5] & 0x400) == 0 )
          goto LABEL_1322;
        updated = sqlite3VdbeMemExpandBlob(v451, 1);
        if ( updated )
          goto LABEL_487;
        v449 = v738;
LABEL_1322:
        v825[1] = (int)v451[4];
        v825[0] = *((_QWORD *)v451 + 1);
        v825[3] = &v9[14 * *((int *)v449 + 3)];
        v826 = *((_WORD *)v449 + 8);
        v452 = *((_WORD *)v449 + 1);
        if ( (v452 & 0x10) != 0 )
          v453 = *(unsigned int *)(v450 + 36);
        else
          v453 = 0;
        kk = sqlite3BtreeInsert(*(_QWORD *)(v450 + 48), v825, (unsigned __int8)v452 & 0x8A, v453);
        *(_DWORD *)(v450 + 32) = 0;
        goto LABEL_959;
      case 0x8Bu:
        v454 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v455 = &v9[14 * *((int *)v20 + 2)];
        if ( (v455[5] & 0x400) != 0 )
        {
          updated = sqlite3VdbeMemExpandBlob(&v9[14 * *((int *)v20 + 2)], 1);
          if ( updated )
            goto LABEL_487;
        }
        kk = sqlite3VdbeSorterWrite(v454, v455);
        goto LABEL_959;
      case 0x8Cu:
        v456 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v457 = *(_QWORD *)(v456 + 48);
        v822[0] = *(_QWORD *)(v456 + 56);
        v823 = *((_WORD *)v20 + 6);
        v824 = 0;
        v822[1] = &v9[14 * *((int *)v20 + 2)];
        kk = sqlite3BtreeIndexMoveto(v457, v822, &v759);
        LODWORD(v739) = kk;
        updated = kk;
        if ( (_DWORD)kk )
          goto LABEL_487;
        if ( v759 )
        {
          v20 = v738;
          if ( *((_WORD *)v738 + 1) )
          {
            kk = v8[6] & 0x10000001;
            if ( kk != 1 )
            {
              updated = 779;
              sqlite3_log(
                779,
                "%s at line %d of [%.10s]",
                "index corruption",
                98281,
                "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
              goto LABEL_487;
            }
          }
          *(_DWORD *)(v456 + 32) = 0;
          *(_DWORD *)(v456 + 36) = 0;
        }
        else
        {
          LOBYTE(v458) = 4;
          kk = sqlite3BtreeDelete(v457, v458);
          LODWORD(v739) = kk;
          updated = kk;
          if ( (_DWORD)kk )
            goto LABEL_487;
          v20 = v738;
          *(_DWORD *)(v456 + 32) = 0;
          *(_DWORD *)(v456 + 36) = 0;
        }
        goto LABEL_571;
      case 0x8Du:
      case 0x8Eu:
        v459 = *((int *)v20 + 1);
        v460 = *(_QWORD *)(v7[15] + 8 * v459);
        if ( **(_BYTE **)(v460 + 48) )
        {
          LODWORD(v739) = sqlite3VdbeHandleMovedCursor(*(_QWORD *)(v7[15] + 8 * v459), 1);
          updated = v739;
          if ( (_DWORD)v739 )
            goto LABEL_487;
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v13 = 1;
        }
        else
        {
          updated = 0;
          LODWORD(v739) = 0;
        }
        if ( !*(_BYTE *)(v460 + 2) )
        {
          v461 = *(_QWORD *)(v460 + 48);
          v747 = 0;
          LODWORD(v739) = sqlite3VdbeIdxRowid(v8, v461, &v747);
          updated = v739;
          if ( (_DWORD)v739 )
            goto LABEL_487;
          if ( *v738 == 0x8D )
          {
            v462 = *(_QWORD *)(v7[15] + 8LL * *((int *)v738 + 3));
            v463 = v747;
            v20 = v738;
            *(_BYTE *)(v462 + 2) = v739;
            *(_QWORD *)(v462 + 80) = v463;
            *(_BYTE *)(v462 + 3) = 1;
            *(_DWORD *)(v462 + 32) = v739;
            kk = *((_QWORD *)v738 + 2);
            *(_QWORD *)(v462 + 16) = kk;
            *(_QWORD *)(v462 + 40) = v460;
          }
          else
          {
            v464 = v7[13] + 56LL * *((int *)v738 + 2);
            if ( (*(_WORD *)(v464 + 20) & 0x9000) != 0 )
            {
              v465 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v738 + 2), v464);
              v20 = v738;
              v466 = (_QWORD *)v465;
              kk = v747;
              *v466 = v747;
            }
            else
            {
              kk = v747;
              v20 = v738;
              *(_WORD *)(v464 + 20) = 4;
              *(_QWORD *)v464 = kk;
            }
          }
          goto LABEL_571;
        }
        kk = (__int64)&v9[14 * *((int *)v738 + 2)];
        if ( (*(_WORD *)(kk + 20) & 0x9000) != 0 )
        {
          kk = vdbeMemClearExternAndSetNull(&v9[14 * *((int *)v738 + 2)], 1);
          v20 = v738;
          goto LABEL_571;
        }
        *(_WORD *)(kk + 20) = 1;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x8Fu:
        kk = v7[15];
        v467 = *(_QWORD *)(kk + 8LL * *((int *)v20 + 1));
        if ( !*(_BYTE *)(v467 + 3) )
          goto LABEL_70;
        kk = sqlite3VdbeFinishMoveto(v467, 1);
        goto LABEL_959;
      case 0x90u:
        v475 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v475 + 20) & 0x9000) != 0 )
          v475 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
        *(_WORD *)(v475 + 20) = 1;
        if ( *((_DWORD *)v8 + 55) > *((_DWORD *)v8 + 58) + 1 )
        {
          updated = 6;
          *((_BYTE *)v7 + 196) = 2;
          goto LABEL_487;
        }
        v476 = *((int *)v738 + 3);
        v477 = v8[4];
        v478 = *((_DWORD *)v738 + 1);
        LODWORD(v750) = 0;
        v479 = *(_QWORD *)(32 * v476 + v477 + 8);
        if ( *(_BYTE *)(v479 + 17) )
        {
          ++*(_DWORD *)(v479 + 20);
          if ( !*(_BYTE *)(v479 + 18) )
            btreeLockCarefully(v479);
        }
        kk = btreeDropTable(v479, v478, &v750);
        updated = kk;
        LODWORD(v739) = kk;
        if ( *(_BYTE *)(v479 + 17) )
        {
          v195 = (*(_DWORD *)(v479 + 20))-- == 1;
          if ( v195 )
            kk = unlockBtreeMutex(v479);
        }
        v480 = (int)v750;
        *(_WORD *)(v475 + 20) = 4;
        *(_QWORD *)v475 = v480;
        if ( updated )
          goto LABEL_486;
        if ( !(_DWORD)v480 )
        {
          v7 = a1;
          goto LABEL_1446;
        }
        v481 = v8[4];
        v482 = v476;
        v483 = *((_DWORD *)v738 + 1);
        for ( nn = *(_QWORD **)(*(_QWORD *)(32 * v476 + v481 + 24) + 16LL); nn; nn = (_QWORD *)*nn )
        {
          v485 = nn[2];
          if ( *(_DWORD *)(v485 + 40) == (_DWORD)v480 )
            *(_DWORD *)(v485 + 40) = v483;
        }
        kk = *(_QWORD *)(32 * v476 + v481 + 24);
        for ( i1 = *(_QWORD **)(kk + 40); i1; i1 = (_QWORD *)*i1 )
        {
          kk = i1[2];
          if ( *(_DWORD *)(kk + 88) == (_DWORD)v480 )
            *(_DWORD *)(kk + 88) = v483;
        }
        LOBYTE(v482) = v476 + 1;
        v755 = v482;
        goto LABEL_1389;
      case 0x91u:
        v762 = 0;
        kk = sqlite3BtreeClearTable(
               *(_QWORD *)(32LL * *((int *)v20 + 2) + v8[4] + 8),
               *((unsigned int *)v20 + 1),
               &v762);
        v20 = v738;
        updated = kk;
        LODWORD(v739) = kk;
        if ( *((_DWORD *)v738 + 3) )
        {
          v7[7] += v762;
          kk = *((int *)v738 + 3);
          if ( (int)kk > 0 )
          {
            v487 = 14 * kk;
            kk = v762;
            *(_QWORD *)&v9[v487] += v762;
            v20 = v738;
          }
        }
        if ( !updated )
          goto LABEL_571;
        goto LABEL_487;
      case 0x92u:
        v488 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        if ( *(_BYTE *)v488 == 1 )
        {
          kk = sqlite3VdbeSorterReset(v8, *(_QWORD *)(v488 + 48));
          v20 = v738;
          goto LABEL_571;
        }
        kk = sqlite3BtreeClearTable(
               *(_QWORD *)(*(_QWORD *)(v488 + 48) + 8LL),
               *(unsigned int *)(*(_QWORD *)(v488 + 48) + 80LL),
               0);
LABEL_959:
        updated = kk;
        LODWORD(v739) = kk;
        v318 = (_DWORD)kk == 0;
        goto LABEL_960;
      case 0x93u:
        v489 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v489 + 20) & 0x9000) != 0 )
          v489 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
        else
          *(_WORD *)(v489 + 20) = 4;
        v490 = v8[4];
        v491 = *((_DWORD *)v738 + 3);
        v492 = 32LL * *((int *)v738 + 1);
        LODWORD(v750) = 0;
        v493 = *(_QWORD *)(v492 + v490 + 8);
        if ( *(_BYTE *)(v493 + 17) )
        {
          ++*(_DWORD *)(v493 + 20);
          if ( !*(_BYTE *)(v493 + 18) )
            btreeLockCarefully(v493);
        }
        updated = btreeCreateTable(v493, &v750, v491);
        LODWORD(v739) = updated;
        if ( *(_BYTE *)(v493 + 17) )
        {
          v195 = (*(_DWORD *)(v493 + 20))-- == 1;
          if ( v195 )
            unlockBtreeMutex(v493);
        }
        if ( updated )
          goto LABEL_487;
        kk = (unsigned int)v750;
        *(_QWORD *)v489 = (unsigned int)v750;
        goto LABEL_569;
      case 0x94u:
        ++*((_BYTE *)v8 + 112);
        kk = sqlite3_exec((_DWORD)v8, *((_QWORD *)v20 + 2), 0, 0, 0);
        --*((_BYTE *)v8 + 112);
        goto LABEL_959;
      case 0x95u:
        v494 = *((int *)v20 + 1);
        if ( *((_QWORD *)v20 + 2) )
        {
          v769[0] = v8;
          v769[1] = v7 + 21;
          v770 = v494;
          v772 = 0;
          v774 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8[4] + 32 * v494 + 8) + 8LL) + 64LL);
          v495 = sqlite3MPrintf(
                   v8,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(v8[4] + 32 * v494),
                   "sqlite_master",
                   *((_QWORD *)v20 + 2));
          if ( !v495 )
          {
            sqlite3ResetAllSchemasOfConnection(v8);
            goto LABEL_1991;
          }
          *((_BYTE *)v8 + 197) = 1;
          v771 = 0;
          v773 = 0;
          LODWORD(v739) = sqlite3_exec((_DWORD)v8, v495, (unsigned int)sqlite3InitCallback, (unsigned int)v769, 0);
          updated = v739;
          if ( !(_DWORD)v739 )
          {
            updated = v771;
            LODWORD(v739) = v771;
            if ( !v771 && !v773 )
            {
              sqlite3_log(
                11,
                "%s at line %d of [%.10s]",
                "database corruption",
                98738,
                "0f80b798b3f4b81a7bb4233c58294edd0f1156f36b6ecf5ab8e83631d468778c");
              updated = 11;
              LODWORD(v739) = 11;
            }
          }
          kk = sqlite3DbFreeNN(v8, v495);
          *((_BYTE *)v8 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v494 + v8[4] + 24), 1);
          *((_DWORD *)v8 + 11) &= ~0x10u;
          kk = sqlite3InitOne(v8, (unsigned int)v494, v7 + 21, *((unsigned __int16 *)v738 + 1));
          *((_DWORD *)v8 + 11) |= 1u;
          updated = kk;
          *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
          LODWORD(v739) = kk;
        }
        if ( !updated )
          goto LABEL_894;
        sqlite3ResetAllSchemasOfConnection(v8);
        v154 = (_QWORD *)v742;
        v11 = v743;
        if ( updated != 7 )
          goto LABEL_489;
        goto LABEL_582;
      case 0x96u:
        kk = sqlite3AnalysisLoad(v8, *((unsigned int *)v20 + 1));
        goto LABEL_959;
      case 0x97u:
        kk = sqlite3HashInsert(*(_QWORD *)(32LL * *((int *)v20 + 1) + v8[4] + 24) + 8LL, *((_QWORD *)v20 + 2), 0);
        if ( kk )
        {
          if ( v8[97] || (v195 = *(_DWORD *)(kk + 44) == 1, --*(_DWORD *)(kk + 44), v195) )
            kk = deleteTable(v8, kk);
        }
        goto LABEL_1426;
      case 0x98u:
        kk = sqlite3HashInsert(*(_QWORD *)(32LL * *((int *)v20 + 1) + v8[4] + 24) + 32LL, *((_QWORD *)v20 + 2), 0);
        v496 = kk;
        if ( !kk )
        {
LABEL_1426:
          *((_DWORD *)v8 + 11) |= 1u;
          v20 = v738;
          goto LABEL_571;
        }
        v497 = *(_QWORD *)(kk + 24);
        v498 = *(_QWORD *)(v497 + 16);
        if ( v498 == v496 )
        {
          *(_QWORD *)(v497 + 16) = *(_QWORD *)(v496 + 40);
          goto LABEL_1435;
        }
        if ( !v498 )
          goto LABEL_1435;
        while ( 1 )
        {
          v499 = (_QWORD *)(v498 + 40);
          v498 = *(_QWORD *)(v498 + 40);
          if ( v498 == v496 )
            break;
          if ( !v498 )
            goto LABEL_1435;
        }
        *v499 = *(_QWORD *)(v496 + 40);
LABEL_1435:
        kk = sqlite3FreeIndex(v8, v496);
        *((_DWORD *)v8 + 11) |= 1u;
        v20 = v738;
        goto LABEL_571;
      case 0x99u:
        v33 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v33 + 20) & 0x9000) != 0 )
        {
          v35 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v33);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v33 = v35;
        }
        *(_WORD *)(v33 + 20) = 8;
LABEL_31:
        kk = *((_QWORD *)v738 + 2);
        *(_QWORD *)v33 = *(_QWORD *)kk;
        goto LABEL_32;
      case 0x9Au:
        kk = sqlite3HashInsert(*(_QWORD *)(32LL * *((int *)v20 + 1) + v8[4] + 24) + 56LL, *((_QWORD *)v20 + 2), 0);
        v500 = kk;
        if ( !kk )
          goto LABEL_894;
        v501 = *(_QWORD *)(kk + 48);
        if ( *(_QWORD *)(kk + 40) != v501 )
          goto LABEL_1444;
        v502 = *(_QWORD *)(findElementWithHash(v501 + 8, *(_QWORD *)(kk + 8), 0) + 16);
        if ( !v502 )
          goto LABEL_1444;
        v503 = *(_QWORD *)(v502 + 88);
        v504 = (_QWORD *)(v502 + 88);
        if ( !v503 )
          goto LABEL_1444;
        while ( v503 != v500 )
        {
          v504 = (_QWORD *)(v503 + 64);
          v503 = *(_QWORD *)(v503 + 64);
          if ( !v503 )
            goto LABEL_1444;
        }
        *v504 = *(_QWORD *)(v503 + 64);
LABEL_1444:
        kk = sqlite3DeleteTrigger(v8, v500);
        *((_DWORD *)v8 + 11) |= 1u;
        v20 = v738;
        goto LABEL_571;
      case 0x9Bu:
        v505 = 14LL * *((int *)v20 + 3);
        v506 = &v9[14 * *((int *)v20 + 1)];
        updated = sqlite3BtreeIntegrityCheck(
                    (_DWORD)v8,
                    *(_QWORD *)(32LL * *((unsigned __int16 *)v20 + 1) + v8[4] + 8),
                    *((_DWORD *)v20 + 4) + 4,
                    *((_DWORD *)v20 + 2),
                    v9[v505] + 1,
                    (__int64)&v760,
                    (__int64)&v764);
        LODWORD(v739) = updated;
        if ( (v506[5] & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v506, v507);
        else
          *((_WORD *)v506 + 10) = 1;
        if ( !v760 )
          goto LABEL_1453;
        if ( updated )
        {
          sqlite3_free(v764);
          goto LABEL_487;
        }
        v509 = v764;
        LOBYTE(v508) = 1;
        *(_QWORD *)&v9[v505] -= v760 - 1;
        sqlite3VdbeMemSetStr(v506, v509, -1, v508, sqlite3_free);
LABEL_1453:
        if ( (v506[5] & 2) != 0 )
        {
          if ( *((_BYTE *)v506 + 22) != v10 )
            sqlite3VdbeMemTranslate(v506, v10);
        }
        else
        {
          *((_BYTE *)v506 + 22) = v10;
        }
        goto LABEL_1826;
      case 0x9Cu:
        v510 = *((int *)v20 + 1);
        v511 = *((int *)v20 + 2);
        v512 = &v9[14 * v510];
        if ( (v512[5] & 0x10) == 0 && (unsigned int)sqlite3VdbeMemSetRowSet(&v9[14 * v510], 1) )
          goto LABEL_1991;
        kk = sqlite3RowSetInsert(*((_QWORD *)v512 + 1), *(_QWORD *)&v9[14 * v511]);
        v20 = v738;
        goto LABEL_571;
      case 0x9Du:
        v539 = *((int *)v20 + 2);
        v540 = v7[13] + 56 * v539;
        if ( (*(_WORD *)(v540 + 20) & 0x9000) != 0 )
        {
          v541 = out2PrereleaseWithClear(v7[13] + 56 * v539, 1);
          v5 = v741;
          v12 = 0x180000000uLL;
          v540 = v541;
        }
        else
        {
          *(_WORD *)(v540 + 20) = 4;
        }
        v542 = *(_QWORD *)(v7[33] + 24)
             + 56LL * (*((_DWORD *)v738 + 1) + *(_DWORD *)(*(_QWORD *)(v7[33] + 16) + 24LL * *(int *)(v7[33] + 76) + 4));
        if ( (*(_WORD *)(v540 + 20) & 0x9000) != 0 )
        {
          kk = vdbeClrCopy(v540, v542, 0x4000);
          v20 = v738;
          goto LABEL_571;
        }
        _XMM0 = *(__m128i *)v542;
        v20 = v738;
        kk = 0x2000;
        v17 = HIDWORD(v739);
        *(_OWORD *)v540 = *(_OWORD *)v542;
        *(_QWORD *)(v540 + 16) = *(_QWORD *)(v542 + 16);
        v195 = (*(_WORD *)(v542 + 20) & 0x2000) == 0;
        v13 = 1;
        if ( !v195 )
          goto LABEL_575;
        *(_WORD *)(v540 + 20) &= 0xCFFFu;
        kk = 0x4000;
        *(_WORD *)(v540 + 20) |= 0x4000u;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0x9Eu:
        if ( (v8[6] & 0x80000) != 0 )
        {
          kk = *((int *)v20 + 2);
          v8[96] += kk;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        else
        {
          kk = *((int *)v20 + 2);
          if ( *((_DWORD *)v20 + 1) )
            v8[95] += kk;
          else
            v7[10] += kk;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
        }
        continue;
      case 0x9Fu:
        v543 = v7[33];
        if ( v543 )
        {
          for ( ; *(_QWORD *)(v543 + 8); v543 = *(_QWORD *)(v543 + 8) )
            ;
          v544 = (__int64 *)(*(_QWORD *)(v543 + 24) + 56LL * *((int *)v738 + 1));
        }
        else
        {
          v544 = (__int64 *)&v9[14 * *((int *)v738 + 1)];
        }
        sqlite3VdbeMemIntegerify(v544, 1);
        v545 = (__int64 *)&v9[14 * *((int *)v738 + 2)];
        sqlite3VdbeMemIntegerify(v545, v546);
        kk = *v545;
        if ( *v544 >= *v545 )
          goto LABEL_894;
        v20 = v738;
        *v544 = kk;
        goto LABEL_571;
      case 0xA0u:
        v548 = *((int *)v20 + 3);
        v549 = 14LL * *((int *)v20 + 1);
        v550 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v550 + 20) & 0x9000) != 0 )
        {
          v551 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
          v5 = v741;
          v12 = 0x180000000uLL;
          v550 = v551;
        }
        else
        {
          *(_WORD *)(v550 + 20) = 4;
        }
        v552 = *(_QWORD *)&v9[v549];
        if ( v552 <= 0 )
          goto LABEL_1535;
        v553 = *(_QWORD *)&v9[14 * v548];
        if ( v553 <= 0 )
          v553 = 0;
        if ( 0x7FFFFFFFFFFFFFFFLL - v552 < v553 )
        {
LABEL_1535:
          v20 = v738;
          kk = -1;
          *(_QWORD *)v550 = -1;
        }
        else
        {
          v20 = v738;
          kk = v552 + v553;
          *(_QWORD *)v550 = v552 + v553;
        }
        goto LABEL_573;
      case 0xA1u:
      case 0xA2u:
        v556 = *((unsigned __int16 *)v20 + 1);
        v557 = 8 * v556 + 104;
        if ( v557 > *((unsigned __int16 *)v8 + 210) )
        {
          if ( *((_DWORD *)v8 + 104) )
          {
            if ( *((_BYTE *)v8 + 103) )
              goto LABEL_1991;
          }
          else
          {
            ++*((_DWORD *)v8 + 109);
          }
          goto LABEL_1557;
        }
        if ( v557 > 0x80 )
          goto LABEL_1552;
        v558 = v8[59];
        if ( v558 )
        {
          v8[59] = *(_QWORD *)v558;
          ++*((_DWORD *)v8 + 108);
        }
        else
        {
          v558 = v8[58];
          if ( v558 )
          {
            v8[58] = *(_QWORD *)v558;
            ++*((_DWORD *)v8 + 108);
          }
          else
          {
LABEL_1552:
            v558 = v8[57];
            if ( v558 )
            {
              v8[57] = *(_QWORD *)v558;
              ++*((_DWORD *)v8 + 108);
            }
            else
            {
              v558 = v8[56];
              if ( !v558 )
              {
                ++*((_DWORD *)v8 + 110);
LABEL_1557:
                v558 = dbMallocRawFinish(v8, v557);
                if ( !v558 )
                  goto LABEL_1991;
                v5 = v741;
                goto LABEL_1559;
              }
              v8[56] = *(_QWORD *)v558;
              ++*((_DWORD *)v8 + 108);
            }
          }
        }
LABEL_1559:
        *(_QWORD *)(v558 + 16) = 0;
        *(_QWORD *)v558 = v558 + 8 * (v556 + 6);
        *(_WORD *)(v558 + 8 * v556 + 68) = 1;
        *(_QWORD *)(v558 + 8 * v556 + 72) = v8;
        *(_DWORD *)(v558 + 8 * v556 + 80) = 0;
        *(_QWORD *)(v558 + 8) = *((_QWORD *)v738 + 2);
        v559 = v738;
        *(_DWORD *)(v558 + 32) = (v738 - v5) / 24;
        *(_QWORD *)(v558 + 24) = v7;
        *(_BYTE *)(v558 + 41) = 0;
        *(_DWORD *)(v558 + 36) = 0;
        *(_BYTE *)(v558 + 40) = v10;
        *(_BYTE *)(v558 + 42) = v556;
        v738[1] = -15;
        *((_QWORD *)v738 + 2) = v558;
        *v738 = -93;
LABEL_1561:
        v560 = (__int64 *)*((_QWORD *)v559 + 2);
        v561 = &v9[14 * *((int *)v559 + 3)];
        v756 = v561;
        if ( (unsigned int *)v560[2] != v561 )
        {
          v560[2] = (__int64)v561;
          v562 = (unsigned int)*((unsigned __int8 *)v560 + 42) - 1;
          if ( (int)v562 >= 0 )
          {
            do
            {
              v560[v562 + 6] = (__int64)&v9[14 * (int)v562 + 14 * *((_DWORD *)v738 + 2)];
              v562 = (unsigned int)(v562 - 1);
            }
            while ( (int)v562 >= 0 );
            v561 = v756;
          }
        }
        ++v561[4];
        v563 = v560 + 6;
        v564 = v560[1];
        v565 = *((unsigned __int8 *)v560 + 42);
        if ( *((_DWORD *)v738 + 1) )
          (*(void (__fastcall **)(__int64 *, __int64, __int64 *))(v564 + 48))(v560, v565, v563);
        else
          (*(void (__fastcall **)(__int64 *, __int64, __int64 *))(v564 + 24))(v560, v565, v563);
        kk = *((unsigned int *)v560 + 9);
        if ( !(_DWORD)kk )
          goto LABEL_894;
        if ( (int)kk > 0 )
        {
          v566 = *v560;
          if ( *v560 )
          {
            v568 = *(unsigned __int16 *)(v566 + 20);
            if ( (v568 & 0x202) == 0x202 && *(_BYTE *)(v566 + 22) == 1 )
            {
              v567 = *(const char **)(v566 + 8);
            }
            else if ( (v568 & 1) != 0 )
            {
              v567 = 0;
            }
            else
            {
              LOBYTE(v568) = 1;
              v567 = (const char *)valueToText(v566, v568);
            }
          }
          else
          {
            v567 = 0;
          }
          sqlite3VdbeError(v7, "%s", v567);
          updated = *((_DWORD *)v560 + 9);
          LODWORD(v739) = updated;
        }
        if ( *((_BYTE *)v560 + 41) )
        {
          v569 = *((int *)v738 - 5);
          if ( (_DWORD)v569 )
          {
            v570 = &v9[14 * v569];
            if ( (v570[5] & 0x9000) != 0 )
            {
              vdbeReleaseAndSetInt64(v570, 1);
            }
            else
            {
              *(_QWORD *)v570 = 1;
              *((_WORD *)v570 + 10) = 4;
            }
          }
          *((_BYTE *)v560 + 41) = 0;
        }
        v571 = *v560;
        if ( (*(_WORD *)(*v560 + 20) & 0x9000) != 0 || *(_DWORD *)(v571 + 32) )
          vdbeMemClear(v571);
        kk = *v560;
        v13 = 1;
        *(_WORD *)(*v560 + 20) = 1;
        *((_DWORD *)v560 + 9) = 0;
        if ( updated )
        {
          v154 = (_QWORD *)v742;
          goto LABEL_488;
        }
        v20 = v738;
LABEL_107:
        v5 = v741;
        goto LABEL_108;
      case 0xA3u:
        v559 = v20;
        goto LABEL_1561;
      case 0xA4u:
      case 0xA5u:
        *((_QWORD *)&v572 + 1) = *((_QWORD *)v20 + 2);
        v573 = *((int *)v20 + 3);
        v574 = &v9[14 * *((int *)v20 + 1)];
        if ( (_DWORD)v573 )
        {
          _XMM0.m128i_i64[0] = 0;
          v801 = 0;
          v802 = 0;
          v804 = 0;
          *(_QWORD *)&v572 = &v9[14 * v573];
          v803 = 0;
          if ( (*(_WORD *)(v572 + 20) & 0x9000) != 0 )
            vdbeMemClearExternAndSetNull(v572, 1);
          else
            *(_WORD *)(v572 + 20) = 1;
          v801 = v572;
          *(_QWORD *)&v802 = v574;
          BYTE8(v803) = *(_BYTE *)(*((_QWORD *)v574 + 3) + 100LL);
          (*(void (__fastcall **)(__int128 *))(*((_QWORD *)&v572 + 1) + 40LL))(&v801);
          updated = DWORD1(v803);
          LODWORD(v739) = DWORD1(v803);
          kk = *((int *)v738 + 3);
          v574 = &v9[14 * kk];
        }
        else
        {
          kk = sqlite3VdbeMemFinalize(&v9[14 * *((int *)v20 + 1)], *((_QWORD *)v20 + 2));
          updated = kk;
          LODWORD(v739) = kk;
        }
        if ( updated )
        {
          v724 = (const char *)sqlite3_value_text(v574);
          sqlite3VdbeError(v7, "%s", v724);
          goto LABEL_487;
        }
        v10 = v737;
        if ( (v574[5] & 2) == 0 )
        {
          v20 = v738;
          *((_BYTE *)v574 + 22) = v737;
          goto LABEL_571;
        }
        if ( *((_BYTE *)v574 + 22) == v737 )
          goto LABEL_894;
        kk = sqlite3VdbeMemTranslate(v574, v737);
        v20 = v738;
        goto LABEL_571;
      case 0xA6u:
        if ( *((_DWORD *)v20 + 1) )
        {
          kk = *((unsigned int *)v7 + 50);
          *((_DWORD *)v7 + 50) = kk ^ ((unsigned __int8)kk ^ (unsigned __int8)(*((_DWORD *)v20 + 2) + 1)) & 3;
          v8 = (_QWORD *)v742;
          v20 += 24;
          v18 = v751;
          continue;
        }
        v599 = v8[1];
        for ( i2 = *((_DWORD *)v20 + 2); v599; v599 = *(_QWORD *)(v599 + 16) )
        {
          kk = *(unsigned int *)(v599 + 200);
          *(_DWORD *)(v599 + 200) = kk ^ ((unsigned __int8)kk ^ (unsigned __int8)(i2 + 1)) & 3;
        }
        goto LABEL_573;
      case 0xA7u:
        kk = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 48LL);
        *(_BYTE *)(kk + 1) |= 0x40u;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0xA8u:
        kk = *(_QWORD *)(*(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1)) + 48LL);
        *(_BYTE *)(kk + 1) &= ~0x40u;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0xA9u:
        v601 = v20[12];
        if ( !v601 )
        {
          kk = 0x400000000LL;
          if ( (v8[6] & 0x400000000LL) != 0 )
            goto LABEL_91;
        }
        kk = v8[4];
        updated = 0;
        LODWORD(v739) = 0;
        v602 = *(_QWORD *)(32LL * *((int *)v20 + 1) + kk + 8);
        if ( !*(_BYTE *)(v602 + 17) )
          goto LABEL_1724;
        v603 = v601 + 1;
        v604 = *((_DWORD *)v20 + 2);
        ++*(_DWORD *)(v602 + 20);
        if ( !*(_BYTE *)(v602 + 18) )
          btreeLockCarefully(v602);
        kk = querySharedCacheTableLock(v602, v604, v603);
        LODWORD(v739) = kk;
        updated = kk;
        if ( (_DWORD)kk )
          goto LABEL_1720;
        v605 = *(_QWORD *)(v602 + 8);
        kk = *(_QWORD *)(v605 + 120);
        if ( !kk )
          goto LABEL_1713;
        while ( *(_DWORD *)(kk + 8) != v604 || *(_QWORD *)kk != v602 )
        {
          kk = *(_QWORD *)(kk + 16);
          if ( !kk )
          {
LABEL_1713:
            kk = sqlite3Malloc(24);
            if ( !kk )
            {
              updated = 7;
              goto LABEL_1719;
            }
            *(_QWORD *)(kk + 12) = 0;
            *(_DWORD *)(kk + 20) = 0;
            *(_DWORD *)(kk + 8) = v604;
            *(_QWORD *)kk = v602;
            *(_QWORD *)(kk + 16) = *(_QWORD *)(v605 + 120);
            *(_QWORD *)(v605 + 120) = kk;
            break;
          }
        }
        if ( v603 > *(_BYTE *)(kk + 12) )
          *(_BYTE *)(kk + 12) = v603;
        updated = 0;
LABEL_1719:
        v7 = a1;
        LODWORD(v739) = updated;
LABEL_1720:
        if ( *(_BYTE *)(v602 + 17) )
        {
          v195 = (*(_DWORD *)(v602 + 20))-- == 1;
          if ( v195 )
            kk = unlockBtreeMutex(v602);
        }
        v17 = HIDWORD(v739);
        v12 = 0x180000000uLL;
        v5 = v741;
        v13 = 1;
LABEL_1724:
        if ( updated )
        {
          if ( (_BYTE)updated == 6 )
            sqlite3VdbeError(v7, "database table is locked: %s", *((const char **)v738 + 2));
          goto LABEL_487;
        }
        v10 = v737;
        v8 = (_QWORD *)v742;
        v20 = v738 + 24;
        v6 = v744;
        v18 = v751;
        continue;
      case 0xAAu:
        v606 = *((_DWORD *)v8 + 137);
        v607 = *((_QWORD *)v20 + 2);
        if ( v606 > 0 && !v8[73] )
        {
          updated = 6;
          LODWORD(v739) = 6;
          if ( !v607 )
            goto LABEL_487;
          kk = sqlite3VtabImportErrmsg(v7, *(_QWORD *)(v607 + 16));
          v318 = 0;
          goto LABEL_960;
        }
        updated = 0;
        LODWORD(v739) = 0;
        if ( !v607 )
        {
LABEL_32:
          v20 = v738;
          goto LABEL_574;
        }
        v608 = *(__int64 **)(v607 + 16);
        v609 = *v608;
        if ( *(_QWORD *)(*v608 + 112) )
        {
          if ( v606 > 0 )
          {
            v610 = 0;
            while ( *(_QWORD *)(v8[73] + 8 * v610) != v607 )
            {
              v610 = (unsigned int)(v610 + 1);
              if ( (int)v610 >= v606 )
                goto LABEL_1736;
            }
            LODWORD(v739) = 0;
            kk = sqlite3VtabImportErrmsg(v7, *(_QWORD *)(v607 + 16));
            v318 = 1;
LABEL_960:
            if ( !v318 )
              goto LABEL_487;
            v20 = v738;
            goto LABEL_571;
          }
LABEL_1736:
          LODWORD(v739) = growVTrans(v8);
          updated = v739;
          if ( !(_DWORD)v739 )
          {
            LODWORD(v739) = (*(__int64 (__fastcall **)(_QWORD))(v609 + 112))(*(_QWORD *)(v607 + 16));
            updated = v739;
            if ( !(_DWORD)v739 )
            {
              v611 = *((_DWORD *)v8 + 188) + *((_DWORD *)v8 + 189);
              *(_QWORD *)(v8[73] + 8LL * (int)(*((_DWORD *)v8 + 137))++) = v607;
              ++*(_DWORD *)(v607 + 24);
              if ( v611 )
              {
                if ( *(_QWORD *)(v609 + 160) )
                {
                  *(_DWORD *)(v607 + 32) = v611;
                  updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v609 + 160))(
                              *(_QWORD *)(v607 + 16),
                              (unsigned int)(v611 - 1));
                  LODWORD(v739) = updated;
                }
              }
            }
          }
        }
        kk = sqlite3VtabImportErrmsg(v7, *(_QWORD *)(v607 + 16));
        v318 = updated == 0;
        goto LABEL_960;
      case 0xABu:
        _XMM0.m128i_i64[0] = 0;
        v775 = 0;
        v779 = 0;
        v776 = 0;
        v777 = v8;
        v778 = 0;
        updated = sqlite3VdbeMemCopy(&v775, &v9[14 * *((int *)v20 + 2)]);
        LODWORD(v739) = updated;
        v612 = 514;
        if ( (WORD6(v776) & 0x202) == 0x202 && BYTE14(v776) == 1 )
        {
          v613 = v776;
        }
        else
        {
          if ( (BYTE12(v776) & 1) != 0 )
            goto LABEL_1764;
          LOBYTE(v612) = 1;
          v613 = valueToText(&v775, v612);
        }
        if ( !v613 )
          goto LABEL_1764;
        Table = sqlite3FindTable(v8, v613, *(_QWORD *)(32LL * *((int *)v738 + 1) + v8[4]));
        v615 = **(const char ***)(Table + 72);
        v616 = *(_QWORD *)(findElementWithHash(v8 + 69, v615, 0) + 16);
        if ( v616 && (v617 = *(_QWORD *)(*(_QWORD *)v616 + 8LL)) != 0 && *(_QWORD *)(*(_QWORD *)v616 + 40LL) )
        {
          LODWORD(v739) = vtabCallConstructor((_DWORD)v8, Table, v616, v617, (__int64)(v7 + 21));
          updated = v739;
          if ( !(_DWORD)v739 )
          {
            v618 = *(_QWORD **)(Table + 80);
            if ( v618 )
            {
              while ( (_QWORD *)*v618 != v8 )
              {
                v618 = (_QWORD *)v618[5];
                if ( !v618 )
                  goto LABEL_1763;
              }
              LODWORD(v739) = growVTrans(v8);
              updated = v739;
              if ( !(_DWORD)v739 )
              {
                for ( i3 = *(_QWORD *)(Table + 80); i3; i3 = *(_QWORD *)(i3 + 40) )
                {
                  if ( *(_QWORD **)i3 == v8 )
                    break;
                }
                *(_QWORD *)(v8[73] + 8LL * (int)(*((_DWORD *)v8 + 137))++) = i3;
                ++*(_DWORD *)(i3 + 24);
              }
            }
          }
        }
        else
        {
          updated = 1;
          v7[21] = sqlite3MPrintf(v8, "no such module: %s", v615);
          LODWORD(v739) = 1;
        }
LABEL_1763:
        v10 = v737;
LABEL_1764:
        kk = 36864;
        if ( (WORD6(v776) & 0x9000) != 0 || (_DWORD)v778 )
          kk = vdbeMemClear(&v775);
        goto LABEL_1767;
      case 0xACu:
        ++*((_DWORD *)v8 + 58);
        updated = 0;
        LODWORD(v739) = 0;
        kk = sqlite3FindTable(v8, *((_QWORD *)v20 + 2), *(_QWORD *)(32LL * *((int *)v20 + 1) + v8[4]));
        v620 = kk;
        if ( !kk )
          goto LABEL_1780;
        if ( *(_BYTE *)(kk + 63) != 1 )
          goto LABEL_1780;
        v621 = *(_QWORD *)(kk + 80);
        if ( !v621 )
          goto LABEL_1780;
        do
        {
          if ( *(int *)(*(_QWORD *)(v621 + 16) + 8LL) > 0 )
          {
            --*((_DWORD *)v8 + 58);
LABEL_2001:
            updated = 6;
            goto LABEL_487;
          }
          v621 = *(_QWORD *)(v621 + 40);
        }
        while ( v621 );
        v622 = vtabDisconnectAll(v8, kk);
        v623 = *(_QWORD *)(v622 + 8);
        v624 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v623 + 40LL);
        if ( !v624 )
          v624 = *(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v623 + 32LL);
        ++*(_DWORD *)(v620 + 44);
        kk = v624(*(_QWORD *)(v622 + 16));
        LODWORD(v739) = kk;
        updated = kk;
        if ( !(_DWORD)kk )
        {
          *(_QWORD *)(v622 + 16) = 0;
          *(_QWORD *)(v620 + 80) = 0;
          kk = sqlite3VtabUnlock(v622);
        }
        if ( v8[97] || (v195 = *(_DWORD *)(v620 + 44) == 1, --*(_DWORD *)(v620 + 44), v195) )
          kk = deleteTable(v8, v620);
LABEL_1780:
        --*((_DWORD *)v8 + 58);
        v318 = updated == 0;
        goto LABEL_960;
      case 0xADu:
        v757 = 0;
        v625 = *(__int64 **)(*((_QWORD *)v20 + 2) + 16LL);
        if ( !v625 )
          goto LABEL_2001;
        v626 = *v625;
        if ( !*v625 )
          goto LABEL_2001;
        LODWORD(v739) = (*(__int64 (__fastcall **)(__int64 *, __int64 ***))(v626 + 48))(v625, &v757);
        updated = v739;
        sqlite3VtabImportErrmsg(v7, v625);
        if ( (_DWORD)v739 )
          goto LABEL_487;
        LOBYTE(v627) = 2;
        *v757 = v625;
        kk = allocateCursor(v7, *((unsigned int *)v738 + 1), 0, v627);
        if ( kk )
        {
          *(_QWORD *)(kk + 48) = v757;
          ++*((_DWORD *)v625 + 2);
          v20 = v738;
          goto LABEL_571;
        }
        (*(void (__fastcall **)(__int64 **))(v626 + 56))(v757);
        v154 = (_QWORD *)v742;
        goto LABEL_581;
      case 0xAEu:
        v628 = *((int *)v20 + 1);
        v629 = *(_QWORD *)(v7[15] + 8 * v628);
        if ( (unsigned int)sqlite3_initialize(v628, 1) )
          goto LABEL_1991;
        v630 = (_QWORD *)sqlite3Malloc(16);
        v631 = v630;
        if ( !v630 )
          goto LABEL_1991;
        *v630 = *(_QWORD *)(v629 + 48);
        v632 = &v9[14 * *((int *)v738 + 3)];
        v630[1] = v632;
        v633 = *((int *)v738 + 2);
        v634 = v7[13] + 56 * v633;
        if ( (*(_WORD *)(v634 + 20) & 0x9000) != 0 )
          v634 = out2PrereleaseWithClear(v7[13] + 56 * v633, v632);
        *(_WORD *)(v634 + 20) = 1;
        vdbeMemClear(v634);
        v20 = v738;
        *(_QWORD *)v634 = "ValueList";
        kk = (__int64)sqlite3VdbeValueListFree;
        *(_QWORD *)(v634 + 8) = v631;
        *(_WORD *)(v634 + 20) = 6657;
        *(_BYTE *)(v634 + 23) = 112;
        *(_QWORD *)(v634 + 48) = sqlite3VdbeValueListFree;
        goto LABEL_571;
      case 0xAFu:
        v658 = *(_QWORD *)(v7[15] + 8LL * *((int *)v20 + 1));
        v132 = (unsigned __int64)&v9[14 * *((int *)v20 + 3)];
        if ( !*(_BYTE *)(v658 + 2) )
        {
          _XMM0.m128i_i64[0] = 0;
          v659 = **(__int64 ***)(v658 + 48);
          v660 = *v659;
          v811 = 0;
          v810 = 0;
          BYTE8(v810) = v737;
          v661 = v20;
          v809[0] = v132;
          v809[1] = 0;
          if ( (v20[2] & 1) != 0 )
          {
            if ( (*(_WORD *)(v132 + 20) & 0x9000) != 0 )
            {
              vdbeMemClearExternAndSetNull(v132, 1);
              v661 = v738;
            }
            *(_WORD *)(v132 + 20) = 1025;
            *(_DWORD *)v132 = 0;
          }
          else
          {
            *(_WORD *)(v132 + 20) &= 0xF241u;
            *(_WORD *)(v132 + 20) |= 1u;
          }
          v662 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD))(v660 + 88))(
                   *(_QWORD *)(v658 + 48),
                   v809,
                   *((unsigned int *)v661 + 2));
          v7 = a1;
          LODWORD(v739) = v662;
          updated = v662;
          kk = sqlite3VtabImportErrmsg(a1, v659);
          if ( SDWORD1(v810) > 0 )
          {
            if ( v132 )
            {
              v664 = *(_WORD *)(v132 + 20);
              v665 = 514;
              if ( (v664 & 0x202) == 0x202 && *(_BYTE *)(v132 + 22) == 1 )
              {
                v663 = *(const char **)(v132 + 8);
              }
              else if ( (v664 & 1) != 0 )
              {
                v663 = 0;
              }
              else
              {
                LOBYTE(v665) = 1;
                v663 = (const char *)valueToText(v132, v665);
              }
            }
            else
            {
              v663 = 0;
            }
            kk = sqlite3VdbeError(a1, "%s", v663);
            updated = DWORD1(v810);
            LODWORD(v739) = DWORD1(v810);
          }
          v10 = v737;
          if ( (*(_BYTE *)(v132 + 20) & 2) != 0 )
          {
            if ( *(_BYTE *)(v132 + 22) == v737 )
            {
LABEL_1767:
              v318 = updated == 0;
            }
            else
            {
              kk = sqlite3VdbeMemTranslate(v132, v737);
              v318 = updated == 0;
            }
          }
          else
          {
            *(_BYTE *)(v132 + 22) = v737;
            v318 = updated == 0;
          }
          goto LABEL_960;
        }
        kk = 36864;
        if ( (*(_WORD *)(v132 + 20) & 0x9000) == 0 )
          goto LABEL_428;
        kk = vdbeMemClearExternAndSetNull(v132, 1);
        v20 = v738;
        goto LABEL_571;
      case 0xB0u:
        v672 = *((_DWORD *)v8 + 12);
        v8[6] |= 0x4000000uLL;
        v673 = *(_QWORD *)(*((_QWORD *)v20 + 2) + 16LL);
        v674 = *((int *)v20 + 1);
        v675 = &v9[14 * v674];
        if ( (v675[5] & 2) != 0 )
        {
          if ( *((_BYTE *)v675 + 22) != 1 )
          {
            LOBYTE(v13) = 1;
            updated = sqlite3VdbeMemTranslate(&v9[14 * v674], v13);
            if ( updated )
              goto LABEL_487;
          }
        }
        else
        {
          *((_BYTE *)v675 + 22) = 1;
        }
        LODWORD(v739) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v673 + 152LL))(
                          v673,
                          *((_QWORD *)v675 + 1));
        updated = v739;
        if ( (v672 & 0x4000000) == 0 )
          v8[6] &= ~0x4000000uLL;
        kk = sqlite3VtabImportErrmsg(v7, v673);
        *((_DWORD *)v7 + 50) &= 0xFFFFFFFC;
        if ( (_DWORD)v739 )
          goto LABEL_487;
        goto LABEL_569;
      case 0xB1u:
        v683 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v683 + 20) & 0x9000) != 0 )
        {
          v684 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), v683);
          v17 = HIDWORD(v739);
          v12 = 0x180000000uLL;
          v5 = v741;
          v683 = v684;
        }
        else
        {
          *(_WORD *)(v683 + 20) = 4;
        }
        kk = *(_QWORD *)(*(_QWORD *)(32LL * *((int *)v738 + 1) + v8[4] + 8) + 8LL);
        *(_QWORD *)v683 = *(unsigned int *)(kk + 64);
        v20 = v738;
        goto LABEL_574;
      case 0xB2u:
        v685 = v7[13] + 56LL * *((int *)v20 + 2);
        if ( (*(_WORD *)(v685 + 20) & 0x9000) != 0 )
          v685 = out2PrereleaseWithClear(v7[13] + 56LL * *((int *)v20 + 2), 1);
        else
          *(_WORD *)(v685 + 20) = 4;
        v686 = 0;
        v687 = *(_QWORD *)(32LL * *((int *)v738 + 1) + v8[4] + 8);
        v688 = *((_DWORD *)v738 + 3);
        if ( v688 )
        {
          v686 = *(_DWORD *)(*(_QWORD *)(v687 + 8) + 64LL);
          if ( v686 < v688 )
            v686 = *((_DWORD *)v738 + 3);
        }
        if ( *(_BYTE *)(v687 + 17) )
        {
          ++*(_DWORD *)(v687 + 20);
          if ( !*(_BYTE *)(v687 + 18) )
            btreeLockCarefully(v687);
        }
        kk = *(_QWORD *)(v687 + 8);
        v689 = *(_QWORD *)kk;
        if ( v686 )
          *(_DWORD *)(v689 + 188) = v686;
        v690 = *(unsigned int *)(v689 + 188);
        if ( *(_BYTE *)(v687 + 17) )
        {
          v195 = (*(_DWORD *)(v687 + 20))-- == 1;
          if ( v195 )
            kk = unlockBtreeMutex(v687);
        }
        *(_QWORD *)v685 = v690;
        goto LABEL_569;
      case 0xB3u:
        kk = 63487;
        LOWORD(v9[14 * *((int *)v20 + 1) + 5]) &= ~0x800u;
        v8 = (_QWORD *)v742;
        v20 += 24;
        v18 = v751;
        continue;
      case 0xB4u:
        v704 = 14LL * *((int *)v20 + 1);
        v705 = filterHash(v9, v20);
        v706 = *(_QWORD *)&v9[v704 + 2];
        v707 = (v705 % (8 * v9[v704 + 4])) & 7;
        v708 = (v705 % (8 * v9[v704 + 4])) >> 3;
        kk = (unsigned int)*(char *)(v708 + v706);
        LODWORD(kk) = kk | (1 << v707);
        *(_BYTE *)(v708 + v706) = kk;
        v20 = v738;
        goto LABEL_571;
      default:
        kk = v22;
        goto LABEL_575;
    }
  }
}

```

## disassembly

```asm
0x1800a4310  mov     r11, rsp
0x1800a4313  push    rbp
0x1800a4314  push    r14
0x1800a4316  lea     rbp, [r11-388h]
0x1800a431d  sub     rsp, 478h
0x1800a4324  mov     rax, cs:__security_cookie
0x1800a432b  xor     rax, rsp
0x1800a432e  mov     [rbp+380h+var_A0], rax
0x1800a4335  mov     r10, [rcx+88h]
0x1800a433c  xor     r9d, r9d
0x1800a433f  mov     [r11+10h], rbx
0x1800a4343  mov     r14, rcx
0x1800a4346  mov     [r11+18h], rsi
0x1800a434a  mov     [r11+20h], rdi
0x1800a434e  mov     [r11-20h], r13
0x1800a4352  mov     r13, [rcx]
0x1800a4355  mov     [r11-28h], r15
0x1800a4359  xor     r11b, r11b
0x1800a435c  mov     r15, [rcx+68h]
0x1800a4360  mov     [rsp+78h], rcx
0x1800a4365  movzx   esi, byte ptr [r13+64h]
0x1800a436a  mov     byte ptr [rsp+480h+var_440], sil
0x1800a436f  mov     [rsp+480h+var_428], r10
0x1800a4374  mov     qword ptr [rsp+480h+var_438], r10
0x1800a4379  mov     [rsp+480h+var_420], r13
0x1800a437e  mov     [rbp+380h+var_3D0], r11d
0x1800a4382  mov     [rsp+480h+var_410], r9
0x1800a4387  mov     [rbp+380h+var_400], r15
0x1800a438b  cmp     [rcx+0D0h], r9d
0x1800a4392  jz      short loc_1800A43A3
0x1800a4394  call    sqlite3VdbeEnter
0x1800a4399  mov     r9, [rsp+480h+var_410]
0x1800a439e  mov     r10, [rsp+480h+var_428]
0x1800a43a3  cmp     qword ptr [r13+210h], 0
0x1800a43ab  jz      short loc_1800A43C5
0x1800a43ad  mov     ecx, [r13+220h]
0x1800a43b4  xor     edx, edx
0x1800a43b6  mov     eax, [r14+0E4h]
0x1800a43bd  div     ecx
0x1800a43bf  sub     ecx, edx
0x1800a43c1  mov     ebx, ecx
0x1800a43c3  jmp     short loc_1800A43CC
0x1800a43c5  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a43cc  cmp     dword ptr [r14+34h], 7
0x1800a43d1  lea     r11, cs:180000000h
0x1800a43d8  mov     [rsp+470h], r12
0x1800a43e0  mov     edx, 1
0x1800a43e5  movaps  [rsp+480h+var_38+8], xmm6
0x1800a43ed  movaps  [rsp+480h+var_48+8], xmm7
0x1800a43f5  movaps  [rsp+480h+var_58+8], xmm8
0x1800a43fe  movaps  [rsp+480h+var_68+8], xmm9
0x1800a4407  movaps  [rsp+480h+var_78+8], xmm10
0x1800a4410  movaps  [rsp+480h+var_88+8], xmm11
0x1800a4419  movaps  [rsp+480h+var_98+8], xmm12
0x1800a4422  mov     [rsp+480h+var_418], rbx
0x1800a4427  jz      loc_1800ACD23
0x1800a442d  mov     dword ptr [r14+34h], 0
0x1800a4435  mov     qword ptr [r14+48h], 0
0x1800a443d  mov     dword ptr [r13+298h], 0
0x1800a4448  mov     eax, [r13+198h]
0x1800a444f  test    eax, eax
0x1800a4451  jnz     loc_1800ACD13
0x1800a4457  movsxd  rax, dword ptr [r14+30h]
0x1800a445b  xor     r12d, r12d
0x1800a445e  movdqa  xmm8, cs:__xmm@00000001000000010000000100000001
0x1800a4467  xor     r8d, r8d
0x1800a446a  movdqa  xmm7, cs:__xmm@00000000000000380000000000000038
0x1800a4472  xor     ebx, ebx
0x1800a4474  movdqa  xmm10, cs:__xmm@00000003000000020000000100000000
0x1800a447d  xorps   xmm9, xmm9
0x1800a4481  movsd   xmm12, cs:__real@c3dfffffffffffff
0x1800a448a  lea     rcx, [rax+rax*2]
0x1800a448e  movsd   xmm11, cs:__real@43dfffffffffffff
0x1800a4497  lea     rcx, [r10+rcx*8]
0x1800a449b  mov     dword ptr [rsp+480h+var_430], r12d
0x1800a44a0  mov     dword ptr [rsp+480h+var_430+4], r8d
0x1800a44a5  mov     [rbp+380h+var_3E0], ebx
0x1800a44a8  movzx   edi, byte ptr [rcx]
0x1800a44ab  inc     r9
0x1800a44ae  mov     qword ptr [rsp+480h+var_438], rcx
0x1800a44b3  mov     [rsp+480h+var_410], r9
0x1800a44b8  cmp     edi, 0B5h; switch 182 cases
0x1800a44be  ja      def_1800A44D2; jumptable 00000001800A44D2 default case
0x1800a44c4  movsxd  rax, edi
0x1800a44c7  mov     ecx, ds:(jpt_1800A44D2 - 180000000h)[r11+rax*4]
0x1800a44cf  add     rcx, r11
0x1800a44d2  jmp     rcx; switch jump
0x1800a44d4  mov     rcx, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 10
0x1800a44d9  movsxd  rax, dword ptr [rcx+4]
0x1800a44dd  sub     rcx, r10
0x1800a44e0  imul    r8, rax, 38h ; '8'
0x1800a44e4  mov     rax, 2AAAAAAAAAAAAAABh
0x1800a44ee  imul    rcx
0x1800a44f1  mov     word ptr [r8+r15+14h], 4
0x1800a44f9  sar     rdx, 2
0x1800a44fd  mov     rax, rdx
0x1800a4500  shr     rax, 3Fh
0x1800a4504  add     rax, rdx
0x1800a4507  cdqe
0x1800a4509  mov     [r8+r15], rax
0x1800a450d  jmp     loc_1800ABDAF; jumptable 00000001800A44D2 case 9
0x1800a4512  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 67
0x1800a4517  movsxd  rax, dword ptr [rax+4]
0x1800a451b  imul    rax, 38h ; '8'
0x1800a451f  test    byte ptr [rax+r15+14h], 4
0x1800a4525  jz      loc_1800A49F8; jumptable 00000001800A44D2 cases 89,93,123
0x1800a452b  mov     rax, [rax+r15]
0x1800a452f  lea     rcx, [rax+rax*2]
0x1800a4533  lea     rcx, [r10+rcx*8]
0x1800a4537  mov     r13, [rsp+480h+var_420]
0x1800a453c  add     rcx, 18h
0x1800a4540  mov     r9, [rsp+480h+var_410]
0x1800a4545  mov     ebx, [rbp+380h+var_3E0]
0x1800a4548  jmp     loc_1800A44A8
0x1800a454d  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 11
0x1800a4552  movsxd  rax, dword ptr [rax+4]
0x1800a4556  imul    rcx, rax, 38h ; '8'
0x1800a455a  mov     rax, qword ptr [rsp+480h+var_438]
0x1800a455f  mov     eax, [rax+0Ch]
0x1800a4562  dec     eax
0x1800a4564  cdqe
0x1800a4566  mov     [rcx+r15], rax
0x1800a456a  mov     word ptr [rcx+r15+14h], 4
0x1800a4572  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a4577  cmp     dword ptr [rcx+8], 0
0x1800a457b  jnz     loc_1800A933C
0x1800a4581  mov     r13, [rsp+480h+var_420]
0x1800a4586  add     rcx, 18h
0x1800a458a  mov     r9, [rsp+480h+var_410]
0x1800a458f  mov     ebx, [rbp+380h+var_3E0]
0x1800a4592  jmp     loc_1800A44A8
0x1800a4597  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 68
0x1800a459c  movsxd  rax, dword ptr [rax+4]
0x1800a45a0  imul    rdx, rax, 38h ; '8'
0x1800a45a4  mov     rax, [rdx+r15]
0x1800a45a8  lea     rcx, [rax+rax*2]
0x1800a45ac  mov     eax, [r10+rcx*8+8]
0x1800a45b1  dec     eax
0x1800a45b3  cdqe
0x1800a45b5  lea     rcx, [rax+rax*2]
0x1800a45b9  lea     rax, [r10+rcx*8]
0x1800a45bd  mov     qword ptr [rsp+480h+var_438], rax
0x1800a45c2  xor     eax, eax
0x1800a45c4  mov     [rdx+r15+14h], ax
0x1800a45ca  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a45cf  jmp     loc_1800A6802
0x1800a45d4  mov     rdi, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 12
0x1800a45d9  movsxd  rax, dword ptr [rdi+4]
0x1800a45dd  sub     rdi, r10
0x1800a45e0  imul    r8, rax, 38h ; '8'
0x1800a45e4  mov     rax, 2AAAAAAAAAAAAAABh
0x1800a45ee  imul    rdi
0x1800a45f1  mov     word ptr [r8+r15+14h], 4
0x1800a45f9  movsxd  rcx, dword ptr [r8+r15]
0x1800a45fd  sar     rdx, 2
0x1800a4601  mov     rax, rdx
0x1800a4604  shr     rax, 3Fh
0x1800a4608  add     rax, rdx
0x1800a460b  lea     rcx, [rcx+rcx*2]
0x1800a460f  cdqe
0x1800a4611  lea     rcx, [r10+rcx*8]
0x1800a4615  mov     [r8+r15], rax
0x1800a4619  jmp     loc_1800A67FD
0x1800a461e  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 69
0x1800a4623  movsxd  rax, dword ptr [rax+0Ch]
0x1800a4627  imul    rcx, rax, 38h ; '8'
0x1800a462b  test    byte ptr [rcx+r15+14h], 1
0x1800a4631  jz      loc_1800A49F8; jumptable 00000001800A44D2 cases 89,93,123
0x1800a4637  mov     rcx, [r14+108h]; jumptable 00000001800A44D2 case 70
0x1800a463e  test    rcx, rcx
0x1800a4641  jz      loc_1800AC5E3
0x1800a4647  mov     rax, qword ptr [rsp+480h+var_438]
0x1800a464c  cmp     dword ptr [rax+4], 0
0x1800a4650  jnz     loc_1800AC5E3
0x1800a4656  mov     rax, [rcx+8]
0x1800a465a  mov     [r14+108h], rax
0x1800a4661  dec     dword ptr [r14+118h]
0x1800a4668  mov     rax, [r14+38h]
0x1800a466c  mov     [r13+78h], rax
0x1800a4670  add     [r13+80h], rax
0x1800a4677  call    sqlite3VdbeFrameRestore
0x1800a467c  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a4681  cmp     dword ptr [rcx+8], 4
0x1800a4685  jnz     short loc_1800A469A
0x1800a4687  cdqe
0x1800a4689  lea     rcx, [rax+rax*2]
0x1800a468d  mov     rax, [r14+88h]
0x1800a4694  mov     eax, [rax+rcx*8+8]
0x1800a4698  dec     eax
0x1800a469a  mov     r10, [r14+88h]
0x1800a46a1  mov     r15, [r14+68h]
0x1800a46a5  cdqe
0x1800a46a7  mov     [rsp+480h+var_428], r10
0x1800a46ac  mov     [rbp+380h+var_400], r15
0x1800a46b0  lea     rcx, [rax+rax*2]
0x1800a46b4  lea     rcx, [r10+rcx*8]
0x1800a46b8  jmp     loc_1800A67F6
0x1800a46bd  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 71
0x1800a46c2  movsxd  rax, dword ptr [rax+8]
0x1800a46c6  imul    rdx, rax, 38h ; '8'
0x1800a46ca  mov     eax, 9000h
0x1800a46cf  add     rdx, [r14+68h]
0x1800a46d3  test    [rdx+14h], ax
0x1800a46d7  jz      short loc_1800A470B
0x1800a46d9  mov     rcx, rdx
0x1800a46dc  call    out2PrereleaseWithClear
0x1800a46e1  mov     r8d, dword ptr [rsp+480h+var_430+4]
0x1800a46e6  lea     r11, cs:180000000h
0x1800a46ed  mov     r10, [rsp+480h+var_428]
0x1800a46f2  mov     rdx, rax
0x1800a46f5  mov     rax, qword ptr [rsp+480h+var_438]
0x1800a46fa  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a46ff  movsxd  rax, dword ptr [rax+4]
0x1800a4703  mov     [rdx], rax
0x1800a4706  jmp     loc_1800A6802
0x1800a470b  mov     rax, qword ptr [rsp+480h+var_438]
0x1800a4710  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a4715  mov     word ptr [rdx+14h], 4
0x1800a471b  movsxd  rax, dword ptr [rax+4]
0x1800a471f  mov     [rdx], rax
0x1800a4722  jmp     loc_1800A6802
0x1800a4727  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 72
0x1800a472c  movsxd  rax, dword ptr [rax+8]
0x1800a4730  imul    rdx, rax, 38h ; '8'
0x1800a4734  mov     eax, 9000h
0x1800a4739  add     rdx, [r14+68h]
0x1800a473d  test    [rdx+14h], ax
0x1800a4741  jz      short loc_1800A4761
0x1800a4743  mov     rcx, rdx
0x1800a4746  call    out2PrereleaseWithClear
0x1800a474b  mov     r8d, dword ptr [rsp+480h+var_430+4]
0x1800a4750  lea     r11, cs:180000000h
0x1800a4757  mov     r10, [rsp+480h+var_428]
0x1800a475c  mov     rdx, rax
0x1800a475f  jmp     short loc_1800A4767
0x1800a4761  mov     word ptr [rdx+14h], 4
0x1800a4767  mov     rax, qword ptr [rsp+480h+var_438]
0x1800a476c  mov     rax, [rax+10h]
0x1800a4770  mov     rcx, [rax]
0x1800a4773  mov     [rdx], rcx
0x1800a4776  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a477b  jmp     loc_1800A6802
0x1800a4780  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 153
0x1800a4785  movsxd  rax, dword ptr [rax+8]
0x1800a4789  imul    rdx, rax, 38h ; '8'
0x1800a478d  mov     eax, 9000h
0x1800a4792  add     rdx, [r14+68h]
0x1800a4796  test    [rdx+14h], ax
0x1800a479a  jz      short loc_1800A47B8
0x1800a479c  mov     rcx, rdx
0x1800a479f  call    out2PrereleaseWithClear
0x1800a47a4  mov     r8d, dword ptr [rsp+480h+var_430+4]
0x1800a47a9  lea     r11, cs:180000000h
0x1800a47b0  mov     r10, [rsp+480h+var_428]
0x1800a47b5  mov     rdx, rax
0x1800a47b8  mov     word ptr [rdx+14h], 8
0x1800a47be  jmp     short loc_1800A4767
0x1800a47c0  mov     rax, qword ptr [rsp+480h+var_438]; jumptable 00000001800A44D2 case 117
0x1800a47c5  movsxd  rax, dword ptr [rax+8]
0x1800a47c9  imul    rbx, rax, 38h ; '8'
0x1800a47cd  mov     eax, 9000h
0x1800a47d2  add     rbx, [r14+68h]
0x1800a47d6  test    [rbx+14h], ax
0x1800a47da  jz      short loc_1800A47E9
0x1800a47dc  mov     rcx, rbx
0x1800a47df  call    out2PrereleaseWithClear
0x1800a47e4  mov     rbx, rax
0x1800a47e7  jmp     short loc_1800A47EF
0x1800a47e9  mov     word ptr [rbx+14h], 4
0x1800a47ef  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a47f4  mov     rdi, [rcx+10h]
0x1800a47f8  test    rdi, rdi
0x1800a47fb  jnz     short loc_1800A4801
0x1800a47fd  xor     eax, eax
0x1800a47ff  jmp     short loc_1800A4813
0x1800a4801  mov     rcx, rdi; Str
0x1800a4804  call    strlen_0
0x1800a4809  mov     rcx, qword ptr [rsp+480h+var_438]
0x1800a480e  and     eax, 3FFFFFFFh
0x1800a4813  mov     [rcx+4], eax
0x1800a4816  cmp     sil, 1
0x1800a481a  jz      loc_1800A48B6
0x1800a4820  mov     r9b, 1
0x1800a4823  mov     [rsp+480h+var_460], 0
0x1800a482c  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800a4833  mov     rdx, rdi
0x1800a4836  mov     rcx, rbx
0x1800a4839  call    sqlite3VdbeMemSetStr
0x1800a483e  mov     dword ptr [rsp+480h+var_430], eax
0x1800a4842  mov     r12d, eax
0x1800a4845  test    eax, eax
0x1800a4847  jnz     loc_1800AC9D9
0x1800a484d  test    byte ptr [rbx+14h], 2
0x1800a4851  jnz     short loc_1800A4859
0x1800a4853  mov     [rbx+16h], sil
0x1800a4857  jmp     short loc_1800A4873
0x1800a4859  cmp     [rbx+16h], sil
0x1800a485d  jz      short loc_1800A4873
0x1800a485f  movzx   edx, sil
0x1800a4863  mov     rcx, rbx
  ... truncated ...
```
