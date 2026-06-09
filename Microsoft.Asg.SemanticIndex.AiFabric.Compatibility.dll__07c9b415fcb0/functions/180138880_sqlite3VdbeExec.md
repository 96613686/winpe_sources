# sqlite3VdbeExec

- ea: `0x180138880`
- end: `0x1801418e4`
- name: `sqlite3VdbeExec`
- size: `36964`
- prototype: ``
- caller_count: `1`
- callee_count: `136`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180132110`

## callees

- `0x1800ba600`
- `0x1800bd1b0`
- `0x1800bd220`
- `0x1800bfd10`
- `0x1800c0200`
- `0x1800c0560`
- `0x1800c0640`
- `0x1800c0c40`
- `0x1800c0db0`
- `0x1800c1600`
- `0x1800c7120`
- `0x1800ca830`
- `0x1800d06c0`
- `0x1800d0a50`
- `0x1800d1180`
- `0x1800d7a40`
- `0x1800d8920`
- `0x1800d9250`
- `0x1800e6050`
- `0x1800e60f0`
- `0x1800e6500`
- `0x1800e6910`
- `0x1800ea520`
- `0x1800eabc0`
- `0x1800eac60`
- `0x1800ead80`
- `0x1800eaed0`
- `0x1800eb640`
- `0x1800f1200`
- `0x1800f6ab0`
- `0x1800f76c0`
- `0x1800fd100`
- `0x1800ffbc0`
- `0x1800ffc80`
- `0x1800ffd30`
- `0x1801002b0`
- `0x180100470`
- `0x180100a30`
- `0x180101030`
- `0x180101590`
- `0x180101bb0`
- `0x180102170`
- `0x1801021d0`
- `0x180102440`
- `0x180102550`
- `0x1801027d0`
- `0x180102d40`
- `0x180102e30`
- `0x1801031b0`
- `0x180103ac0`

## string_xrefs

- `0x180140c9b`: `cannot open savepoint - SQL statements in progress`
- `0x18014126b`: `cannot commit transaction - SQL statements in progress`
- `0x180141344`: `cannot rollback - no transaction is active`
- `0x18014134b`: `cannot commit - no transaction is active`
- `0x180141471`: `abort due to ROLLBACK`

## pseudocode

```c
__int64 __fastcall sqlite3VdbeExec(__int64 *a1)
{
  __int64 v2; // r14
  __int64 v3; // r12
  unsigned __int8 *v4; // r15
  unsigned __int64 v5; // r11
  __int64 *v6; // r13
  __int64 v7; // r9
  __int64 v8; // r8
  unsigned __int8 v9; // r10
  unsigned __int64 v10; // rsi
  unsigned __int64 v11; // rdi
  __int64 v12; // rdx
  __int64 nn; // rax
  __int64 v14; // rdi
  __m128i si128; // xmm8
  __m128i v16; // xmm9
  unsigned __int8 *v17; // r15
  __int64 v18; // rbx
  unsigned __int64 v19; // rsi
  __int64 v20; // kr00_8
  unsigned __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  _QWORD *v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned __int8 *v37; // r9
  __int64 v38; // rax
  __int64 v39; // rbx
  __int64 v40; // rax
  __int64 v41; // rdi
  int v42; // eax
  int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rcx
  _DWORD *v48; // r9
  __int64 v49; // rcx
  __int16 *v50; // rbx
  int v51; // edi
  __int16 v52; // si
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rdx
  int v57; // edi
  __int64 v58; // rsi
  __int64 v59; // rdi
  __int16 v60; // ax
  int v61; // ecx
  __m128i *v62; // rbx
  int v63; // esi
  unsigned __int64 v64; // rdi
  unsigned __int64 v65; // rbx
  unsigned int v66; // esi
  __m128i *v67; // rdi
  __m128i *v68; // rbx
  __int16 v69; // ax
  __int64 v70; // rdx
  __int64 v71; // rcx
  unsigned __int64 v72; // r8
  __int64 v73; // rdx
  unsigned __int64 v74; // r15
  __int16 v75; // r12
  unsigned __int64 v76; // rdi
  unsigned __int64 v77; // rbx
  int v78; // eax
  __int16 v79; // si
  int v80; // eax
  int v81; // edx
  __int64 v82; // r14
  unsigned __int64 v83; // rsi
  __int16 v84; // bx
  unsigned __int64 v85; // rdi
  unsigned __int64 v86; // r14
  __int16 v87; // cx
  __int16 v88; // bx
  __int16 v89; // ax
  __int64 v90; // r8
  __int16 v91; // ax
  double v92; // xmm6_8
  __int16 v93; // ax
  __int64 v94; // rbx
  __int64 v95; // rdx
  __int64 v96; // r8
  __int64 v97; // rax
  unsigned __int64 v98; // rsi
  unsigned __int64 v99; // rcx
  unsigned __int64 v100; // rdi
  __int64 v101; // rbx
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // rax
  __int64 v105; // rdx
  unsigned __int8 v106; // cl
  unsigned __int64 v107; // r8
  _QWORD *v108; // rbx
  __int64 v109; // rax
  unsigned __int64 v110; // rbx
  __int16 v111; // cx
  __int64 v112; // rcx
  unsigned __int64 v113; // rbx
  __int64 *v114; // r15
  unsigned __int64 v115; // r14
  __int16 v116; // si
  __int16 v117; // di
  __int64 v118; // rax
  char v119; // al
  __int16 v120; // ax
  __int64 v121; // rdx
  int v122; // eax
  unsigned __int8 v123; // cl
  unsigned int v124; // ecx
  char v125; // dl
  __int64 v126; // r13
  __int64 v127; // rcx
  int v128; // esi
  int v129; // r8d
  __int64 v130; // rbx
  unsigned int v131; // r9d
  _QWORD *v132; // r14
  int v133; // edx
  unsigned __int64 v134; // r12
  int v135; // edi
  unsigned __int64 v136; // r15
  unsigned __int8 *v137; // r9
  unsigned __int64 v138; // rcx
  __int16 v139; // ax
  int v140; // ebx
  int v141; // eax
  int v142; // ebx
  __int64 *v143; // rax
  __int64 v144; // rdx
  __int64 v145; // rcx
  int v146; // eax
  __int64 v147; // r8
  __int64 v148; // r9
  unsigned __int64 v149; // rdx
  unsigned __int64 v150; // rcx
  unsigned __int64 v151; // rbx
  __int16 v152; // ax
  unsigned __int64 v153; // rdi
  unsigned __int64 v154; // rbx
  __int64 v155; // r8
  __int64 v156; // r9
  unsigned int v157; // edx
  unsigned __int64 v158; // rax
  int v159; // ecx
  __int64 v160; // rax
  __int64 v161; // rcx
  __int64 v162; // rdx
  __int64 v163; // rcx
  int v164; // ecx
  __int64 v165; // rdx
  unsigned __int64 v166; // rax
  __int64 v167; // rbx
  unsigned int v168; // r14d
  unsigned int *v169; // r13
  int v170; // eax
  __int64 v171; // rdi
  int v172; // eax
  int v173; // edx
  int v174; // ecx
  unsigned __int8 *v175; // rcx
  __int64 v176; // rax
  __int64 v177; // rcx
  int v178; // eax
  unsigned int v179; // eax
  int Varint32; // eax
  __int64 v181; // rax
  __int64 v182; // r10
  int v183; // edx
  int v184; // ecx
  __int64 v185; // r12
  __int64 v186; // r14
  unsigned int *v187; // rcx
  unsigned __int8 *v188; // rsi
  unsigned __int64 v189; // r15
  unsigned __int64 v190; // r13
  __int64 v191; // rdi
  __int64 v192; // rax
  unsigned __int8 v193; // al
  int v194; // esi
  __m128i *v195; // rcx
  int v196; // eax
  unsigned __int8 *v197; // rdx
  __int64 v198; // rsi
  const void *v199; // r14
  __int64 v200; // rbx
  __int64 v201; // rdx
  char v202; // al
  char v203; // al
  unsigned int v204; // eax
  unsigned int v205; // r9d
  int v206; // esi
  __int64 v207; // r14
  __int64 v208; // r15
  unsigned __int64 v209; // rbx
  __int64 v210; // rdi
  __int16 v211; // ax
  char v212; // cl
  __int16 v213; // ax
  __int16 v214; // ax
  unsigned __int16 v215; // cx
  bool v216; // zf
  double v217; // rdx
  __int16 v218; // cx
  _BYTE *v219; // rdi
  unsigned __int64 n; // rbx
  __int16 v221; // cx
  __int16 v222; // ax
  __int16 v223; // cx
  __int16 v224; // cx
  __int64 v225; // r8
  unsigned __int64 v226; // rdx
  __int64 v227; // r14
  __int64 v228; // r13
  _BYTE *v229; // rdi
  unsigned __int64 v230; // r11
  __int64 v231; // rcx
  unsigned int *v232; // rsi
  _WORD *v233; // rbx
  unsigned int *v234; // r15
  unsigned __int16 v235; // ax
  unsigned int v236; // ebx
  __int64 v237; // r8
  unsigned int v238; // esi
  __int64 v239; // rax
  int v240; // ecx
  unsigned __int64 ii; // rax
  int v242; // edx
  unsigned __int64 jj; // rax
  int v244; // ecx
  unsigned __int64 kk; // rax
  __int64 v246; // rdi
  __int64 v247; // rbx
  __int64 v248; // rdx
  _BYTE *v249; // rsi
  _BYTE *v250; // rbx
  _BYTE *v251; // rsi
  int v252; // eax
  int *v253; // r14
  int *mm; // rdi
  __int64 v255; // rdx
  unsigned __int64 v256; // rcx
  __int64 v257; // rdx
  unsigned __int64 v258; // rcx
  unsigned __int64 v259; // rcx
  size_t v260; // rax
  int v261; // eax
  __int64 v262; // rcx
  __int64 v263; // rdx
  __int64 v264; // rdx
  __int64 v265; // rbx
  __int64 v266; // rax
  unsigned int v267; // r10d
  const char *v268; // rsi
  size_t v269; // rdi
  _QWORD *v270; // rbx
  unsigned int v271; // r13d
  const char **v272; // r12
  const char *i; // rdx
  __int64 v274; // rax
  int v275; // r15d
  __int64 v276; // rax
  int v277; // edi
  int v278; // r14d
  __int64 v279; // rbx
  int v280; // edi
  __int64 v281; // rbx
  __int64 j; // rax
  __int64 k; // rcx
  unsigned int v284; // ebx
  unsigned int v285; // r12d
  __int64 v286; // rdx
  __int64 v287; // rsi
  __int64 v288; // rdi
  __int64 v289; // rbx
  char v290; // al
  __int64 v291; // rcx
  __int64 v292; // rdx
  int v293; // r8d
  __int64 *v294; // rax
  __int64 v295; // rdx
  __int64 v296; // rcx
  unsigned int v297; // eax
  int v298; // edx
  __int64 v299; // rbx
  _QWORD *v300; // rcx
  int v301; // ebx
  __int64 v302; // rdx
  __int64 v303; // rax
  __int64 v304; // rdi
  __int64 v305; // rbx
  unsigned int updated; // eax
  unsigned __int8 *v307; // r9
  __int64 v308; // rdi
  unsigned int v309; // edi
  __int64 v310; // r15
  __int64 v311; // r14
  int v312; // r12d
  __int64 v313; // rcx
  __int64 v314; // rax
  __int64 v315; // r13
  int v316; // esi
  unsigned __int8 v317; // cl
  _DWORD *v318; // rbx
  unsigned __int8 v319; // al
  __int64 Cursor; // rax
  unsigned int v321; // eax
  __int64 v322; // rbx
  __int64 v323; // rax
  int v324; // ecx
  __int64 v325; // rax
  __int64 v326; // rdx
  __int64 v327; // rbx
  __int64 v328; // rax
  __int64 v329; // rbx
  __int64 v330; // rcx
  __int64 v331; // rax
  unsigned int v332; // eax
  unsigned int v333; // eax
  __int64 v334; // rsi
  unsigned int v335; // eax
  unsigned int v336; // eax
  int v337; // ecx
  __int64 v338; // rax
  __int64 v339; // rdx
  __int64 v340; // rcx
  __int64 v341; // rdx
  __int64 v342; // rsi
  unsigned __int64 v343; // rdi
  __int16 v344; // r14
  __int64 v345; // rax
  __int16 v346; // cx
  __int64 v347; // r15
  _BYTE *v348; // rcx
  int v349; // eax
  __int64 *v350; // rdi
  unsigned int v351; // eax
  __int64 v352; // rdx
  int v353; // ecx
  char v354; // r14
  char v355; // al
  __int64 v356; // rax
  __int64 v357; // rcx
  __int64 v358; // r8
  __int64 v359; // rdx
  bool v360; // zf
  __int64 v361; // rcx
  __int64 v362; // rdi
  int v363; // esi
  __int64 v364; // rbx
  unsigned int v365; // r10d
  int v366; // edx
  int v367; // ecx
  __int64 v368; // rax
  __int64 v369; // rdx
  __int64 v370; // r8
  int v371; // ebx
  bool v372; // sf
  __int64 v373; // rcx
  unsigned int v374; // eax
  int v375; // r8d
  __int64 v376; // rdx
  int v377; // ecx
  __int64 v378; // rdx
  __int64 v379; // rbx
  unsigned __int64 v380; // rcx
  int *v381; // rsi
  unsigned int v382; // eax
  __int64 v383; // rax
  __int64 v384; // rdi
  int v385; // ecx
  __int64 v386; // rcx
  __int64 v387; // rcx
  __int64 v388; // rdi
  __int64 v389; // rbx
  unsigned int v390; // eax
  __int64 v391; // rdx
  __int64 v392; // rax
  __int64 v393; // rbx
  unsigned int v394; // edi
  __int64 v395; // r14
  __int64 v396; // rsi
  _BYTE *v397; // rcx
  __int64 v398; // rdx
  __int64 i1; // rcx
  __int64 *v400; // rdi
  __int64 v401; // rbx
  int v402; // edi
  __int64 v403; // rcx
  int *v404; // rdx
  __int64 v405; // rbx
  _QWORD *v406; // rdi
  __int64 v407; // rsi
  __int64 v408; // r9
  __int64 v409; // rdx
  __int64 v410; // rax
  __int64 v411; // r8
  unsigned __int8 *v412; // r9
  int v413; // r15d
  __int64 v414; // rdi
  __int64 v415; // rsi
  __int64 v416; // r14
  __int64 v417; // rbx
  __int64 (__fastcall *v418)(_QWORD, __int64, __int64, _QWORD, _QWORD); // r10
  __int64 v419; // r8
  int v420; // ebx
  __int64 v421; // rdx
  __int64 v422; // rdi
  __int64 v423; // rsi
  unsigned __int64 v424; // r15
  __int64 v425; // r14
  __int64 v426; // rax
  __int64 v427; // rax
  unsigned int *v428; // r8
  unsigned int *v429; // rdx
  int v430; // ecx
  _BYTE *v431; // rax
  unsigned __int64 v432; // rbx
  __int64 v433; // rax
  __int64 v434; // rax
  const void *v435; // rsi
  int *v436; // rdi
  size_t v437; // rdi
  __int64 v438; // rbx
  __int64 v439; // rdi
  __int64 v440; // rdx
  __int64 v441; // rdx
  __int64 v442; // rdi
  __int64 v443; // rax
  __int64 v444; // rbx
  __int64 *v445; // rcx
  __int64 v446; // rbx
  __int64 v447; // rbx
  __int64 v448; // rdx
  __int64 v449; // rdi
  _BYTE *v450; // rcx
  unsigned int v451; // eax
  __int64 v452; // rbx
  unsigned int v453; // eax
  int v454; // esi
  unsigned int v455; // eax
  __int64 v456; // rcx
  __int64 v457; // rax
  unsigned int v458; // r11d
  int v459; // edi
  __int64 v460; // rsi
  __int64 v461; // rbx
  unsigned int v462; // eax
  __int64 v463; // rsi
  __int64 v464; // rdi
  unsigned __int8 *v465; // rbx
  __int64 v466; // rcx
  __int64 v467; // rdx
  __int64 v468; // rbx
  int v469; // r12d
  __int64 v470; // rcx
  unsigned int v471; // eax
  __int64 v472; // rcx
  __int64 v473; // rdx
  unsigned __int8 *v474; // r9
  __int64 v475; // rdi
  unsigned __int64 v476; // rbx
  unsigned __int8 v477; // r8
  __int64 v478; // r9
  __int64 v479; // rdi
  unsigned __int64 v480; // rbx
  __int64 v481; // rbx
  __int64 v482; // rdi
  __int64 v483; // rdx
  __int64 v484; // rcx
  __int64 v485; // rbx
  __int64 v486; // rdx
  __int64 v487; // rdx
  __int64 v488; // rax
  __int64 v489; // rdx
  __int64 v490; // rax
  _QWORD *v491; // rdx
  __int64 v492; // rcx
  bool v493; // cf
  __int64 v494; // rdx
  __int64 v495; // rbx
  unsigned int v496; // r10d
  int v497; // edx
  int v498; // ecx
  __int64 v499; // rax
  int v500; // ebx
  int v501; // ebx
  unsigned __int8 *v502; // r9
  __int64 v503; // rbx
  __int64 v504; // rax
  int v505; // esi
  __int64 v506; // rcx
  __int64 v507; // rdx
  __int64 v508; // rdi
  __int64 v509; // rdx
  __int64 v510; // r9
  int v511; // r8d
  _QWORD *i2; // rcx
  __int64 v513; // rax
  _QWORD *i3; // rcx
  __int64 v515; // rcx
  __int64 v516; // rcx
  unsigned __int8 *v517; // r9
  __int64 v518; // rbx
  __int64 v519; // rax
  __int64 v520; // rcx
  __int64 v521; // r8
  __int64 v522; // rax
  __int64 v523; // rbx
  char v524; // di
  int v525; // esi
  const char *v526; // rbx
  int v527; // eax
  __int64 v528; // rbx
  __int64 v529; // rax
  __int64 v530; // r8
  __int64 v531; // rax
  __int64 v532; // rcx
  _QWORD *v533; // rdx
  __int64 v534; // rbx
  __int64 v535; // rcx
  __int64 v536; // rdx
  __int64 v537; // rax
  _QWORD *v538; // rdx
  __int64 v539; // rdi
  unsigned __int64 v540; // rbx
  __int64 v541; // rdx
  __int64 v542; // r9
  unsigned int v543; // r12d
  __int64 v544; // rdx
  unsigned __int64 v545; // rbx
  unsigned __int64 v546; // rsi
  __int64 (__fastcall *v547)(_QWORD); // rdx
  unsigned __int64 v548; // rbx
  _QWORD *v549; // rdi
  unsigned __int64 v550; // rdi
  __int64 v551; // rbx
  __int16 v552; // ax
  __int64 *v553; // rax
  __int64 v554; // rdi
  __int64 v555; // rax
  unsigned __int64 v556; // rax
  int v557; // esi
  bool v558; // sf
  __int64 *v559; // r12
  unsigned __int64 v560; // r15
  int v561; // edx
  int v562; // edi
  int v563; // r14d
  _DWORD *v564; // rax
  _DWORD *v565; // rbx
  _DWORD *v566; // rax
  _DWORD *v567; // rcx
  __int64 v568; // rcx
  __int64 v569; // rdx
  void *v570; // rcx
  __int64 v571; // rax
  __int64 v572; // r9
  __int64 v573; // rax
  __int64 v574; // r8
  int v575; // edx
  __int64 v576; // rcx
  __int64 v577; // rdx
  __int64 i4; // rcx
  __int64 *v579; // rdi
  __int64 *v580; // rbx
  __int64 v581; // rcx
  __int64 *v582; // rbx
  __int64 *v583; // rdi
  __int64 v584; // rdx
  __int64 v585; // rax
  __int64 v586; // r8
  __int64 v587; // rcx
  __int64 v588; // rcx
  __int64 v589; // rcx
  __int64 v590; // rbx
  __int64 v591; // rax
  unsigned __int8 *v592; // r9
  __int64 *v593; // rbx
  unsigned __int64 v594; // r10
  __int64 v595; // rdx
  int v596; // r9d
  __int64 *v597; // r8
  int v598; // eax
  __int64 *v599; // r8
  __int64 v600; // rax
  __int64 v601; // rdx
  __int64 v602; // r9
  __int64 v603; // rcx
  const char *v604; // rax
  __int64 v605; // rdx
  __int64 v606; // rax
  unsigned __int64 v607; // rax
  __int64 v608; // rcx
  __int128 v609; // rdi
  __int64 v610; // rax
  unsigned __int64 v611; // rbx
  unsigned int v612; // eax
  int v613; // edx
  unsigned __int64 v614; // rbx
  _QWORD *v615; // rcx
  _QWORD *v616; // rcx
  __int64 v617; // r15
  __int64 v618; // r13
  __int64 v619; // rax
  _QWORD *v620; // rbx
  unsigned int v621; // r14d
  unsigned int v622; // esi
  const char *v623; // rcx
  __int64 v624; // rcx
  unsigned int v625; // r12d
  int v626; // eax
  unsigned int v627; // edi
  char v628; // al
  const char *v629; // rcx
  __int64 v630; // rax
  unsigned __int64 v631; // r9
  __int64 v632; // rcx
  __int64 v633; // rdi
  unsigned __int32 v634; // esi
  unsigned __int32 v635; // ebx
  unsigned __int32 v636; // r14d
  __int64 v637; // rcx
  __int64 m; // rax
  __int64 v639; // rdx
  unsigned int v640; // eax
  __int64 v641; // rdx
  int i5; // r8d
  __int64 v643; // rdx
  __int64 v644; // rbx
  int v645; // edi
  __int64 *v646; // rax
  __int64 v647; // rdi
  __int64 v648; // rcx
  _QWORD *v649; // rax
  int v650; // edx
  unsigned int v651; // eax
  __int16 v652; // cx
  __int64 v653; // rdx
  __int64 v654; // rax
  __int64 v655; // rsi
  const char *v656; // rdi
  __int64 v657; // r8
  __int64 v658; // r9
  _QWORD *v659; // rax
  __int64 i6; // rdx
  __int64 *v661; // rbx
  __int64 v662; // rdi
  unsigned __int8 *v663; // r9
  unsigned __int64 v664; // rbx
  _QWORD *v665; // rdi
  __int64 v666; // rdx
  __int64 *v667; // rcx
  __int64 v668; // rax
  __int64 v669; // rbx
  _QWORD *v670; // rax
  _QWORD *v671; // rdi
  unsigned __int64 v672; // rdx
  __int64 v673; // rcx
  __int64 v674; // rbx
  __int64 v675; // rdx
  __int64 v676; // r13
  int *v677; // rbx
  unsigned int v678; // r12d
  __int64 **v679; // rsi
  __int64 v680; // r11
  __int64 v681; // rdi
  __m128i v682; // xmm4
  signed int v683; // r9d
  __int64 *v684; // r15
  __int64 v685; // rdx
  __int64 v686; // r14
  __int64 v687; // rcx
  unsigned int v688; // r8d
  __m128i v689; // xmm3
  __m128i v690; // xmm1
  unsigned int v691; // eax
  __m128i v696; // xmm2
  int v700; // r8d
  __int64 v701; // rax
  __int64 v702; // rdi
  unsigned __int64 v703; // rbx
  unsigned __int8 *v704; // rcx
  __int64 *v705; // rsi
  __int64 v706; // r14
  const char *v707; // rax
  __int16 v708; // cx
  __int64 v709; // rdx
  __int64 v710; // rdi
  __int64 **v711; // rcx
  __int64 *v712; // rbx
  __int64 v713; // rsi
  int v714; // edi
  int v715; // edi
  __int64 v716; // rsi
  __int64 v717; // rax
  unsigned __int64 v718; // rbx
  __int64 *v719; // rbx
  __int64 v720; // r10
  __int64 v721; // rdx
  char v722; // di
  __int64 v723; // r8
  __int64 v724; // rax
  unsigned __int64 v725; // rcx
  int v726; // ecx
  __int64 v727; // rax
  __int64 v728; // r8
  __int64 v729; // rax
  unsigned int v730; // edx
  __int64 v731; // r9
  unsigned int v732; // ecx
  __int64 v733; // rcx
  __int64 v734; // r15
  __int64 v735; // rax
  unsigned __int64 v736; // rbx
  __int64 v737; // rdx
  int v738; // r9d
  __int64 v739; // r8
  int v740; // eax
  __int16 v741; // cx
  __int64 v742; // rdx
  const char *v743; // rax
  int v744; // r14d
  __int64 *v745; // rdi
  unsigned __int64 v746; // rbx
  int v747; // esi
  void (__fastcall *v748)(_QWORD); // rax
  int v749; // eax
  __int64 v750; // rdx
  unsigned __int64 v751; // rcx
  __int64 v752; // rdx
  unsigned __int64 v753; // rcx
  __int64 v754; // rbx
  unsigned __int64 v755; // rax
  __int64 v756; // rcx
  unsigned __int64 v757; // rdx
  unsigned __int64 v758; // r8
  __int64 v759; // rbx
  unsigned __int64 v760; // rax
  unsigned __int64 v761; // rdx
  int v762; // r8d
  const char *v763; // r9
  __int64 v764; // rbx
  int v765; // edx
  __int64 v766; // rax
  __int64 v767; // rcx
  int v768; // ecx
  __int64 v769; // rax
  unsigned __int8 *v770; // rbx
  int v771; // eax
  char *v772; // rax
  __int16 v773; // cx
  __int64 v774; // rdx
  const char *v775; // r8
  __int64 v776; // rbx
  int v777; // eax
  char v778; // al
  int v779; // ebx
  int v780; // ecx
  char v781; // al
  unsigned __int8 *v782; // rcx
  int v783; // eax
  const char *v784; // rdx
  const char *v785; // r8
  unsigned int (__fastcall *v786)(_QWORD); // rdx
  unsigned __int8 v788; // [rsp+40h] [rbp-C0h]
  unsigned int Table; // [rsp+44h] [rbp-BCh]
  unsigned int v790; // [rsp+44h] [rbp-BCh]
  unsigned __int8 *v791; // [rsp+48h] [rbp-B8h]
  unsigned int v792; // [rsp+50h] [rbp-B0h]
  __int64 v793; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v794; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v795; // [rsp+68h] [rbp-98h]
  __int64 v796; // [rsp+70h] [rbp-90h]
  unsigned int v798; // [rsp+80h] [rbp-80h] BYREF
  BOOL v799; // [rsp+84h] [rbp-7Ch] BYREF
  char v800; // [rsp+88h] [rbp-78h]
  __int64 v801; // [rsp+90h] [rbp-70h] BYREF
  int v802; // [rsp+98h] [rbp-68h]
  unsigned int *v803; // [rsp+A0h] [rbp-60h]
  int v804; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v805; // [rsp+B0h] [rbp-50h]
  int v806; // [rsp+B8h] [rbp-48h]
  int v807; // [rsp+BCh] [rbp-44h] BYREF
  int v808; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v809; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v810[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v811; // [rsp+ECh] [rbp-14h]
  char v812; // [rsp+EEh] [rbp-12h]
  _QWORD v813[3]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v814; // [rsp+114h] [rbp+14h]
  char v815; // [rsp+116h] [rbp+16h]
  __int64 **v816; // [rsp+120h] [rbp+20h] BYREF
  const char *v817; // [rsp+128h] [rbp+28h] BYREF
  __int64 v818; // [rsp+130h] [rbp+30h] BYREF
  __int128 v819; // [rsp+138h] [rbp+38h] BYREF
  __int128 v820; // [rsp+148h] [rbp+48h]
  __int128 v821; // [rsp+158h] [rbp+58h]
  __int64 v822; // [rsp+168h] [rbp+68h]
  _QWORD v823[2]; // [rsp+170h] [rbp+70h] BYREF
  int v824; // [rsp+180h] [rbp+80h]
  unsigned int v825; // [rsp+184h] [rbp+84h]
  int v826; // [rsp+188h] [rbp+88h]
  int v827; // [rsp+18Ch] [rbp+8Ch]
  int v828; // [rsp+190h] [rbp+90h]
  __int64 v829; // [rsp+198h] [rbp+98h] BYREF
  __int128 v830; // [rsp+1A0h] [rbp+A0h]
  __int64 v831; // [rsp+1B0h] [rbp+B0h]
  __int128 v832; // [rsp+1B8h] [rbp+B8h]
  __int64 v833; // [rsp+1C8h] [rbp+C8h]
  __int64 v834; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v835; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 v836; // [rsp+1ECh] [rbp+ECh]
  char v837; // [rsp+1EEh] [rbp+EEh]
  char v838[8]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v839; // [rsp+200h] [rbp+100h]
  unsigned int v840; // [rsp+208h] [rbp+108h]
  __int16 v841; // [rsp+20Ch] [rbp+10Ch]
  __int64 v842; // [rsp+210h] [rbp+110h]
  int v843; // [rsp+218h] [rbp+118h]
  char v844[8]; // [rsp+230h] [rbp+130h] BYREF
  __int64 v845; // [rsp+238h] [rbp+138h]
  unsigned int v846; // [rsp+240h] [rbp+140h]
  __int16 v847; // [rsp+244h] [rbp+144h]
  __int64 v848; // [rsp+248h] [rbp+148h]
  int v849; // [rsp+250h] [rbp+150h]
  __int64 v850; // [rsp+268h] [rbp+168h] BYREF
  __int64 v851; // [rsp+270h] [rbp+170h]
  __int64 v852; // [rsp+278h] [rbp+178h]
  int v853; // [rsp+28Ch] [rbp+18Ch]
  int v854; // [rsp+290h] [rbp+190h]
  __int128 v855; // [rsp+298h] [rbp+198h] BYREF
  __int128 v856; // [rsp+2A8h] [rbp+1A8h]
  __int128 v857; // [rsp+2B8h] [rbp+1B8h]
  __int64 v858; // [rsp+2C8h] [rbp+1C8h]
  _QWORD v859[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v860; // [rsp+2E0h] [rbp+1E0h]
  __int128 v861; // [rsp+2F0h] [rbp+1F0h]
  __int64 v862; // [rsp+300h] [rbp+200h]
  _QWORD v863[3]; // [rsp+308h] [rbp+208h] BYREF
  __int16 v864; // [rsp+324h] [rbp+224h]
  char v865; // [rsp+326h] [rbp+226h]
  char v866; // [rsp+32Ah] [rbp+22Ah]
  _QWORD v867[3]; // [rsp+330h] [rbp+230h] BYREF
  __int16 v868; // [rsp+34Ch] [rbp+24Ch]
  char v869; // [rsp+34Eh] [rbp+24Eh]
  _QWORD v870[4]; // [rsp+358h] [rbp+258h] BYREF
  __int16 v871; // [rsp+378h] [rbp+278h]
  char v872; // [rsp+390h] [rbp+290h] BYREF
  int v873; // [rsp+394h] [rbp+294h]
  __int64 v874; // [rsp+398h] [rbp+298h]
  __int64 v875; // [rsp+3E0h] [rbp+2E0h] BYREF
  int v876; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int64 v877; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v878; // [rsp+3F8h] [rbp+2F8h] BYREF
  __int64 v879; // [rsp+400h] [rbp+300h] BYREF
  __int128 v880; // [rsp+408h] [rbp+308h] BYREF
  __int128 v881; // [rsp+418h] [rbp+318h]
  __m128i v882; // [rsp+428h] [rbp+328h]
  __int64 v883; // [rsp+438h] [rbp+338h]
  int v884; // [rsp+440h] [rbp+340h]
  int v885; // [rsp+444h] [rbp+344h] BYREF
  int v886; // [rsp+448h] [rbp+348h] BYREF

  v2 = *a1;
  v3 = 0;
  v4 = (unsigned __int8 *)a1[17];
  v5 = a1[13];
  v6 = a1;
  v800 = 0;
  v7 = 0;
  v8 = 0;
  v9 = *(_BYTE *)(v2 + 100);
  v10 = 0;
  v788 = v9;
  v793 = (__int64)v4;
  v791 = v4;
  Table = 0;
  v796 = v2;
  v792 = 0;
  v805 = 0;
  v794 = v5;
  v802 = 0;
  if ( *(_QWORD *)(v2 + 512) )
    v11 = (unsigned int)(*(_DWORD *)(v2 + 528) - *((_DWORD *)a1 + 57) % *(_DWORD *)(v2 + 528));
  else
    v11 = -1;
  v12 = 0x180000000uLL;
  v795 = v11;
  if ( *((_DWORD *)a1 + 13) == 7 )
    goto LABEL_83;
  *((_DWORD *)a1 + 13) = 0;
  a1[9] = 0;
  *(_DWORD *)(v2 + 648) = 0;
  if ( *(_DWORD *)(v2 + 392) )
    goto LABEL_1926;
  nn = *((int *)a1 + 12);
  v14 = (__int64)v4;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v16 = _mm_load_si128((const __m128i *)&_xmm);
  v17 = &v4[24 * nn];
LABEL_7:
  while ( 2 )
  {
    v18 = *v17;
    v19 = v10 + 1;
    v791 = v17;
    v805 = v19;
    v20 = nn;
    nn = (int)v18;
    switch ( (int)v18 )
    {
      case 0:
        v267 = *((_DWORD *)v17 + 1);
        v268 = (const char *)*((_QWORD *)v17 + 2);
        v798 = v267;
        if ( !v267 )
        {
          if ( *(int *)(v2 + 224) <= 0 )
          {
            if ( v268 )
              v269 = strlen(v268) & 0x3FFFFFFF;
            else
              LODWORD(v269) = 0;
            Table = sqlite3VtabSavepoint(v2, 0, (unsigned int)(*(_DWORD *)(v2 + 736) + *(_DWORD *)(v2 + 740)), v7);
            LODWORD(v7) = Table;
            if ( Table )
              goto LABEL_289;
            nn = sqlite3DbMallocRawNN(v2, (unsigned int)v269 + 33LL);
            v270 = (_QWORD *)nn;
            if ( nn )
            {
              *(_QWORD *)nn = nn + 32;
              memmove((void *)(nn + 32), v268, (unsigned int)(v269 + 1));
              if ( *(_BYTE *)(v2 + 101) )
              {
                *(_BYTE *)(v2 + 101) = 0;
                *(_BYTE *)(v2 + 109) = 1;
              }
              else
              {
                ++*(_DWORD *)(v2 + 736);
              }
              v270[3] = *(_QWORD *)(v2 + 720);
              *(_QWORD *)(v2 + 720) = v270;
              v270[1] = *(_QWORD *)(v2 + 744);
              nn = *(_QWORD *)(v2 + 752);
              v270[2] = nn;
            }
            v7 = 0;
            goto LABEL_774;
          }
          sqlite3VdbeError(v6, "cannot open savepoint - SQL statements in progress", v8, v7);
          LODWORD(v7) = 5;
          goto LABEL_288;
        }
        v271 = 0;
        v272 = *(const char ***)(v2 + 720);
        if ( !v272 )
        {
LABEL_742:
          v6 = a1;
          sqlite3VdbeError(a1, "no such savepoint: %s", v268);
LABEL_743:
          LODWORD(v7) = 1;
          Table = 1;
          goto LABEL_289;
        }
LABEL_727:
        for ( i = *v272; ; ++i )
        {
          v274 = *(unsigned __int8 *)i;
          v8 = (unsigned __int8)i[v268 - *v272];
          if ( (_BYTE)v274 == (_BYTE)v8 )
          {
            if ( !(_BYTE)v274 )
            {
              if ( *(int *)(v2 + 224) <= 0 || v267 != 1 )
              {
                if ( v272[3] || !*(_BYTE *)(v2 + 109) )
                {
                  v275 = 0;
                }
                else
                {
                  v275 = 1;
                  if ( v267 == 1 )
                  {
                    v790 = sqlite3VdbeCheckFk(a1, 1);
                    if ( v790 )
                    {
                      v285 = v790;
                      v6 = a1;
                    }
                    else
                    {
                      *(_BYTE *)(v2 + 101) = 1;
                      if ( (unsigned int)sqlite3VdbeHalt(a1) != 5 )
                      {
                        v7 = *((unsigned int *)a1 + 13);
                        Table = v7;
                        if ( !(_DWORD)v7 )
                        {
                          *(_BYTE *)(v2 + 109) = 0;
                          goto LABEL_763;
                        }
                        *(_BYTE *)(v2 + 101) = 0;
                        v6 = a1;
LABEL_289:
                        v11 = v795;
LABEL_290:
                        v4 = (unsigned __int8 *)v793;
LABEL_291:
                        if ( *(_BYTE *)(v2 + 103) )
                        {
                          LODWORD(v7) = 7;
                          Table = 7;
                        }
                        else if ( (_DWORD)v7 == 8458 )
                        {
                          sqlite3_log(
                            11,
                            "%s at line %d of [%.10s]",
                            "database corruption",
                            102462,
                            "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
                          LODWORD(v7) = 11;
                          Table = 11;
                        }
                        if ( !v6[21] && (_DWORD)v7 != 3082 )
                        {
                          v785 = "unknown error";
                          switch ( (_DWORD)v7 )
                          {
                            case 0x64:
                              v785 = "another row available";
                              break;
                            case 0x65:
                              v785 = "no more rows available";
                              break;
                            case 0x204:
                              v785 = "abort due to ROLLBACK";
                              break;
                            default:
                              if ( (unsigned __int8)v7 < 0x1Du )
                              {
                                _mm_lfence();
                                if ( off_180272F90[(unsigned __int8)v7] )
                                  v785 = off_180272F90[(unsigned __int8)v7];
                              }
                              break;
                          }
                          sqlite3VdbeError(v6, "%s", v785);
                        }
                        *((_DWORD *)v6 + 13) = Table;
                        sqlite3SystemError(v2, Table, v8);
                        sqlite3_log(
                          Table,
                          "statement aborts at %d: [%s] %s",
                          (v791 - v4) / 24,
                          (const char *)v6[31],
                          (const char *)v6[21]);
                        if ( *((_BYTE *)v6 + 199) == 2 )
                          sqlite3VdbeHalt(v6);
                        if ( Table == 3082 )
                        {
                          sqlite3OomFault(v2);
                        }
                        else if ( Table == 11 && !*(_BYTE *)(v2 + 101) )
                        {
                          *(_QWORD *)(v2 + 48) |= 0x200000000uLL;
                        }
                        v285 = 1;
                        if ( v800 )
                          sqlite3ResetOneSchema(v2);
LABEL_1958:
                        v19 = v805;
                        goto LABEL_1959;
                      }
                      v285 = 5;
                      v6 = a1;
                      *((_DWORD *)a1 + 12) = (__int64)&v791[-v14] / 24;
                      *(_BYTE *)(v2 + 101) = 0;
                      *((_DWORD *)a1 + 13) = 5;
                    }
LABEL_1957:
                    v4 = (unsigned __int8 *)v793;
                    v11 = v795;
                    goto LABEL_1958;
                  }
                }
                v276 = v796;
                v271 = *(_DWORD *)(v2 + 736) + ~v271;
                if ( v267 == 2 )
                {
                  v277 = 0;
                  v278 = *(_DWORD *)(v2 + 44) & 1;
                  if ( *(int *)(v796 + 40) > 0 )
                  {
                    v279 = 0;
                    do
                    {
                      Table = sqlite3BtreeTripAllCursors(*(_QWORD *)(*(_QWORD *)(v276 + 32) + v279 + 8), 516, v278 ^ 1u);
                      v7 = Table;
                      if ( Table )
                        goto LABEL_1840;
                      v276 = v796;
                      ++v277;
                      v279 += 32;
                    }
                    while ( v277 < *(_DWORD *)(v796 + 40) );
                    v267 = v798;
LABEL_754:
                    v280 = 0;
                    if ( *(int *)(v276 + 40) > 0 )
                    {
                      v281 = 0;
                      while ( 1 )
                      {
                        Table = sqlite3BtreeSavepoint(*(_QWORD *)(*(_QWORD *)(v276 + 32) + v281 + 8), v267, v271, v7);
                        v7 = Table;
                        if ( Table )
                          break;
                        v276 = v796;
                        ++v280;
                        v267 = v798;
                        v281 += 32;
                        if ( v280 >= *(_DWORD *)(v796 + 40) )
                          goto LABEL_758;
                      }
LABEL_1840:
                      v2 = v796;
LABEL_1841:
                      v6 = a1;
                      goto LABEL_289;
                    }
LABEL_758:
                    v216 = v278 == 0;
                    v2 = v796;
                    if ( !v216 )
                    {
                      for ( j = *(_QWORD *)(v796 + 8); j; j = *(_QWORD *)(j + 16) )
                      {
                        *(_DWORD *)(j + 200) &= ~2u;
                        *(_DWORD *)(j + 200) |= 1u;
                      }
                      sqlite3ResetAllSchemasOfConnection(v796);
                      *(_DWORD *)(v796 + 44) |= 1u;
                      v7 = Table;
                    }
                    if ( (_DWORD)v7 )
                      goto LABEL_1841;
LABEL_763:
                    for ( k = *(_QWORD *)(v2 + 720); (const char **)k != v272; k = *(_QWORD *)(v2 + 720) )
                    {
                      *(_QWORD *)(v2 + 720) = *(_QWORD *)(k + 24);
                      sqlite3DbFreeNN(v2);
                      --*(_DWORD *)(v2 + 736);
                    }
                    v284 = v798;
                    if ( v798 == 1 )
                    {
                      *(_QWORD *)(v2 + 720) = v272[3];
                      nn = sqlite3DbFreeNN(v2);
                      if ( !v275 )
                      {
                        --*(_DWORD *)(v2 + 736);
LABEL_770:
                        nn = sqlite3VtabSavepoint(v2, v284, v271, v7);
                        Table = nn;
                        v7 = (unsigned int)nn;
                        if ( (_DWORD)nn )
                          goto LABEL_1841;
LABEL_773:
                        v6 = a1;
                        v3 = 0;
LABEL_774:
                        if ( *((_BYTE *)v6 + 199) == 3 )
                        {
                          v285 = 101;
                          goto LABEL_1957;
                        }
LABEL_68:
                        v17 = v791;
LABEL_69:
                        v5 = v794;
                        v9 = v788;
LABEL_164:
                        v14 = v793;
LABEL_165:
                        v8 = v792;
LABEL_166:
                        v12 = 0x180000000uLL;
LABEL_167:
                        v10 = v805;
                        v17 += 24;
                        goto LABEL_7;
                      }
                    }
                    else
                    {
                      *(_QWORD *)(v2 + 744) = v272[1];
                      nn = (__int64)v272[2];
                      *(_QWORD *)(v2 + 752) = nn;
                      if ( !v275 || v284 == 2 )
                        goto LABEL_770;
                    }
                    v7 = Table;
                    goto LABEL_773;
                  }
                }
                else
                {
                  v278 = 0;
                }
                v7 = Table;
                goto LABEL_754;
              }
              v6 = a1;
              sqlite3VdbeError(a1, "cannot release savepoint - SQL statements in progress");
              LODWORD(v7) = 5;
LABEL_288:
              Table = v7;
              goto LABEL_289;
            }
          }
          else if ( *((unsigned __int8 *)qword_18026E880 + v274) != *((unsigned __int8 *)qword_18026E880 + v8) )
          {
            v272 = (const char **)v272[3];
            ++v271;
            if ( !v272 )
              goto LABEL_742;
            goto LABEL_727;
          }
        }
      case 1:
        v779 = *((_DWORD *)v17 + 1);
        v780 = *((_DWORD *)v17 + 2);
        if ( v779 == *(unsigned __int8 *)(v2 + 101) )
        {
          if ( v779 )
          {
            v784 = "cannot commit - no transaction is active";
            if ( v780 )
              v784 = "cannot rollback - no transaction is active";
            sqlite3VdbeError(v6, v784, v8, v7);
          }
          else
          {
            sqlite3VdbeError(v6, "cannot start a transaction within a transaction", v8, v7);
          }
          goto LABEL_743;
        }
        if ( v780 )
        {
          sqlite3RollbackAll(v2, 516, v8, v7);
          v781 = 1;
        }
        else
        {
          if ( v779 && *(int *)(v2 + 224) > 0 )
          {
            sqlite3VdbeError(v6, "cannot commit transaction - SQL statements in progress", v8, v7);
            LODWORD(v7) = 5;
            goto LABEL_288;
          }
          v285 = sqlite3VdbeCheckFk(v6, 1);
          if ( v285 )
          {
LABEL_1906:
            v11 = v795;
            v4 = (unsigned __int8 *)v793;
            goto LABEL_1959;
          }
          v781 = v779;
        }
        *(_BYTE *)(v2 + 101) = v781;
        if ( (unsigned int)sqlite3VdbeHalt(v6) == 5 )
        {
          v782 = &v17[-v14];
          v285 = 5;
          v11 = v795;
          v4 = (unsigned __int8 *)v793;
          *((_DWORD *)v6 + 12) = (__int64)v782 / 24;
          *(_BYTE *)(v2 + 101) = 1 - v779;
          *((_DWORD *)v6 + 13) = 5;
        }
        else
        {
          sqlite3CloseSavepoints(v2);
          v783 = 101;
          v11 = v795;
          if ( *((_DWORD *)v6 + 13) )
            v783 = 1;
          v4 = (unsigned __int8 *)v793;
          v285 = v783;
        }
        goto LABEL_1959;
      case 2:
        v804 = 0;
        v286 = *((unsigned int *)v17 + 2);
        if ( (_DWORD)v286 )
        {
          nn = *(_QWORD *)(v2 + 48);
          v8 = 0x200100000LL;
          if ( (nn & 0x200100000LL) != 0 )
          {
            LODWORD(v7) = 8;
            if ( (nn & 0x100000) == 0 )
              LODWORD(v7) = 11;
            Table = v7;
            goto LABEL_289;
          }
        }
        v287 = *(_QWORD *)(v2 + 32);
        v288 = 32LL * *((int *)v17 + 1);
        v289 = *(_QWORD *)(v288 + v287 + 8);
        if ( !v289 )
          goto LABEL_805;
        if ( *(_BYTE *)(v289 + 17) || (v290 = *(_BYTE *)(v289 + 16)) == 0 || v290 == 1 && (_DWORD)v286 )
        {
          nn = btreeBeginTrans(*(_QWORD *)(v288 + v287 + 8), v286, &v804, v7);
        }
        else
        {
          v8 = *(_QWORD *)(v289 + 8);
          nn = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 24) + 80LL) + 40LL));
          v804 = nn;
          if ( !(_DWORD)v286 )
          {
            v7 = 0;
            Table = 0;
            goto LABEL_793;
          }
          nn = *(_QWORD *)v289;
          v291 = *(_QWORD *)v8;
          v292 = *(unsigned int *)(*(_QWORD *)v289 + 736LL);
          if ( (int)v292 <= *(_DWORD *)(*(_QWORD *)v8 + 128LL) || !*(_BYTE *)(v291 + 10) )
          {
            v7 = 0;
            Table = 0;
            goto LABEL_791;
          }
          _mm_lfence();
          nn = pagerOpenSavepoint(v291, v292, v8, v7);
        }
        Table = nn;
        v7 = (unsigned int)nn;
LABEL_791:
        if ( (_DWORD)v7 )
        {
          v4 = (unsigned __int8 *)v793;
          v11 = v795;
          if ( (_BYTE)v7 != 5 )
            goto LABEL_291;
          v285 = Table;
          *((_DWORD *)v6 + 12) = (__int64)&v791[-v793] / 24;
          *((_DWORD *)v6 + 13) = v7;
          goto LABEL_1958;
        }
        v5 = v794;
        v9 = v788;
LABEL_793:
        if ( (v6[25] & 0x20) != 0 && *((_DWORD *)v17 + 2) && (!*(_BYTE *)(v2 + 101) || *(int *)(v2 + 220) > 1) )
        {
          v293 = *((_DWORD *)v6 + 16);
          if ( !v293 )
          {
            v293 = ++*(_DWORD *)(v2 + 740) + *(_DWORD *)(v2 + 736);
            *((_DWORD *)v6 + 16) = v293;
          }
          Table = sqlite3VtabSavepoint(v2, 0, (unsigned int)(v293 - 1), v7);
          v7 = Table;
          if ( !Table )
          {
            v294 = *(__int64 **)(v289 + 8);
            v295 = *((unsigned int *)v6 + 16);
            v296 = *v294;
            if ( (int)v295 <= *(_DWORD *)(*v294 + 128) || *(_BYTE *)(v296 + 10) == (_BYTE)Table )
            {
              v7 = 0;
              Table = 0;
            }
            else
            {
              _mm_lfence();
              v297 = pagerOpenSavepoint(v296, v295, v8, Table);
              v7 = v297;
              Table = v297;
            }
          }
          v5 = v794;
          v9 = v788;
          v6[11] = *(_QWORD *)(v2 + 744);
          nn = *(_QWORD *)(v2 + 752);
          v6[12] = nn;
LABEL_805:
          if ( (_DWORD)v7 )
            goto LABEL_289;
        }
        if ( !*((_WORD *)v17 + 1) )
          goto LABEL_164;
        if ( v804 == *((_DWORD *)v17 + 3) )
        {
          nn = *((unsigned int *)v17 + 4);
          if ( *(_DWORD *)(*(_QWORD *)(v288 + v287 + 24) + 4LL) == (_DWORD)nn )
            goto LABEL_164;
        }
        if ( v6[21] )
          sqlite3DbFreeNN(v2);
        v772 = (char *)sqlite3DbMallocRawNN(v2, 28);
        if ( v772 )
          strcpy(v772, "database schema has changed");
        v6[21] = (__int64)v772;
        if ( **(_DWORD **)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 24) != v804 )
          sqlite3ResetOneSchema(v2);
        LODWORD(v7) = 17;
        *((_DWORD *)v6 + 50) = v6[25] & 0xFFFFFFEC | 1;
        goto LABEL_288;
      case 3:
        v884 = 0;
        v886 = -1;
        v885 = -1;
        v612 = sqlite3Checkpoint(v2, *((_DWORD *)v17 + 1), *((_DWORD *)v17 + 2), (unsigned int)&v885, (__int64)&v886);
        Table = v612;
        v7 = v612;
        if ( v612 )
        {
          if ( v612 != 5 )
            goto LABEL_289;
          Table = 0;
          v613 = 1;
          v3 = 0;
        }
        else
        {
          v613 = v884;
        }
        v614 = v794 + 56LL * *((int *)v17 + 3);
        _mm_lfence();
        if ( (*(_WORD *)(v614 + 20) & 0x9000) != 0 )
        {
          vdbeReleaseAndSetInt64(v794 + 56LL * *((int *)v17 + 3), v613, v8, v612);
        }
        else
        {
          *(_QWORD *)v614 = v613;
          *(_WORD *)(v614 + 20) = 4;
        }
        v615 = (_QWORD *)(v614 + 56);
        if ( (*(_WORD *)(v614 + 76) & 0x9000) != 0 )
        {
          vdbeReleaseAndSetInt64(v615, v885, v8, v7);
        }
        else
        {
          *v615 = v885;
          *(_WORD *)(v614 + 76) = 4;
        }
        v616 = (_QWORD *)(v614 + 112);
        nn = v886;
        if ( (*(_WORD *)(v614 + 132) & 0x9000) != 0 )
        {
          nn = vdbeReleaseAndSetInt64(v616, v886, v8, v7);
        }
        else
        {
          *v616 = v886;
          *(_WORD *)(v614 + 132) = 4;
        }
        goto LABEL_129;
      case 4:
        v617 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v617 + 20) & 0x9000) != 0 )
          v617 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v791 + 2), 0x180000000uLL);
        else
          *(_WORD *)(v617 + 20) = 4;
        v618 = *(_QWORD *)(32LL * *((int *)v791 + 1) + *(_QWORD *)(v2 + 32) + 8);
        v619 = *(_QWORD *)(v618 + 8);
        v620 = *(_QWORD **)v619;
        v621 = *(unsigned __int8 *)(*(_QWORD *)v619 + 9LL);
        v622 = v621;
        if ( *((_DWORD *)v791 + 3) != -1 )
          v622 = *((_DWORD *)v791 + 3);
        if ( *((_BYTE *)v620 + 21) >= 3u || *(_QWORD *)v620[10] && (__int64)v620[12] > 0 )
          v622 = *(unsigned __int8 *)(*(_QWORD *)v619 + 9LL);
        if ( *((_BYTE *)v620 + 19) || (char *)*v620 == byte_180338410 )
          v623 = byte_18026D0A4;
        else
          v623 = (const char *)v620[27];
        if ( v622 == 5 )
        {
          if ( !v623
            || (strlen(v623) & 0x3FFFFFFF) == 0
            || (v624 = *(_QWORD *)v620[9], *((_BYTE *)v620 + 17))
            || !*((_BYTE *)v620 + 8) && (*(int *)v624 < 2 || !*(_QWORD *)(v624 + 104)) )
          {
            v622 = v621;
LABEL_1536:
            v625 = Table;
            goto LABEL_1537;
          }
        }
        if ( v622 == v621 || v621 != 5 && v622 != 5 )
          goto LABEL_1536;
        if ( !*(_BYTE *)(v796 + 101) || *(int *)(v796 + 220) > 1 )
        {
          v6 = a1;
          v775 = "out of";
          Table = 1;
          if ( v622 == 5 )
            v775 = "into";
          sqlite3VdbeError(a1, "cannot change %s wal mode from within a transaction", v775);
          LODWORD(v7) = 1;
          v2 = v796;
          goto LABEL_289;
        }
        if ( v621 != 5 )
        {
          if ( v621 == 4 )
            sqlite3PagerSetJournalMode(v620, 2);
          if ( Table )
            goto LABEL_1538;
          goto LABEL_1568;
        }
        v627 = 0;
        if ( v620[41] )
          goto LABEL_1967;
        v876 = 0;
        v628 = *((_BYTE *)v620 + 22);
        if ( (!v628 || v628 == 5)
          && (*((_BYTE *)v620 + 17)
           || (v627 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v620[9] + 56LL))(v620[9], 1)) == 0)
          && *((_BYTE *)v620 + 22) != 5 )
        {
          *((_BYTE *)v620 + 22) = 1;
        }
        if ( !v627 )
        {
          v627 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *))(*v620 + 56LL))(*v620, v620[42], 0, &v876);
          if ( !v627 && (!v876 || (v627 = pagerOpenWal(v620)) == 0) )
          {
LABEL_1967:
            if ( v620[41] )
            {
              v627 = pagerExclusiveLock(v620);
              if ( !v627 )
              {
                Table = sqlite3WalClose(
                          v620[41],
                          v796,
                          *((unsigned __int8 *)v620 + 15),
                          *((_DWORD *)v620 + 50),
                          v620[39]);
                v620[41] = 0;
                v627 = Table;
                pagerFixMaplimit(v620);
                if ( Table )
                {
                  if ( !*((_BYTE *)v620 + 8) )
                  {
                    pagerUnlockDb(v620, 1);
                    goto LABEL_1538;
                  }
                }
              }
            }
          }
        }
        Table = v627;
        if ( !v627 )
        {
          sqlite3PagerSetJournalMode(v620, v622);
LABEL_1568:
          v625 = sqlite3BtreeSetVersion(v618, (unsigned int)(v622 == 5) + 1);
          Table = v625;
LABEL_1537:
          if ( !v625 )
            goto LABEL_1539;
        }
LABEL_1538:
        v622 = v621;
LABEL_1539:
        v626 = sqlite3PagerSetJournalMode(v620, v622);
        *(_WORD *)(v617 + 20) = 8706;
        if ( v626 == 6 )
        {
          *(_QWORD *)(v617 + 8) = 0;
          nn = 0;
        }
        else
        {
          v629 = off_18026F470[v626];
          *(_QWORD *)(v617 + 8) = v629;
          if ( v629 )
            nn = strlen(v629) & 0x3FFFFFFF;
          else
            nn = 0;
        }
        v9 = v788;
        *(_DWORD *)(v617 + 16) = nn;
        *(_BYTE *)(v617 + 22) = 1;
        if ( v788 != 1 )
        {
          nn = sqlite3VdbeMemTranslate(v617, v788);
          v9 = v788;
        }
        v6 = a1;
LABEL_1575:
        v7 = Table;
        v2 = v796;
        if ( Table )
          goto LABEL_289;
        goto LABEL_161;
      case 5:
        v630 = *((int *)v17 + 2);
        if ( (_DWORD)v630 )
          v631 = v5 + 56 * v630;
        else
          v631 = 0;
        nn = sqlite3RunVacuum(v6 + 21, v2, *((unsigned int *)v17 + 1), v631);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 6:
        v675 = 56LL * *((int *)v17 + 3);
        v676 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v677 = (int *)(v5 + v675 + 56);
        v678 = *(_DWORD *)(v675 + v5);
        v679 = *(__int64 ***)(v676 + 48);
        v680 = a1[14];
        v681 = *v677;
        v682 = _mm_unpacklo_epi64((__m128i)(unsigned __int64)v677, (__m128i)(unsigned __int64)v677);
        v683 = 0;
        v684 = *v679;
        v685 = 0;
        v686 = **v679;
        if ( (int)v681 >= 8 && _isa_available >= 6 )
        {
          v687 = v680 + 32;
          v688 = 4;
          do
          {
            v689 = _mm_move_epi64(v16);
            v690 = _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v683), 0), v689);
            v691 = v688 + 2;
            v687 += 64;
            v683 += 8;
            v685 += 8;
            _XMM0 = _mm_cvtepi32_epi64(_mm_add_epi32(v690, _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            _XMM0 = _mm_cvtepi32_epi64(
                      _mm_add_epi32(
                        _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v688 - 2), 0), v689),
                        _mm_move_epi64(si128)));
            *(__m128i *)(v687 - 96) = _mm_add_epi64(_XMM1, v682);
            __asm { vpmullq xmm1, xmm0, xmm7 }
            v696 = _mm_cvtsi32_si128(v688);
            *(__m128i *)(v687 - 80) = _mm_add_epi64(_XMM1, v682);
            v688 += 8;
            _XMM0 = _mm_cvtepi32_epi64(_mm_add_epi32(_mm_add_epi32(_mm_shuffle_epi32(v696, 0), v689), _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            *(__m128i *)(v687 - 64) = _mm_add_epi64(_XMM1, v682);
            _XMM0 = _mm_cvtepi32_epi64(
                      _mm_add_epi32(
                        _mm_add_epi32(_mm_shuffle_epi32(_mm_cvtsi32_si128(v691), 0), v689),
                        _mm_move_epi64(si128)));
            __asm { vpmullq xmm1, xmm0, xmm7 }
            *(__m128i *)(v687 - 48) = _mm_add_epi64(_XMM1, v682);
          }
          while ( v683 < (int)(v681 - (v681 & 7)) );
        }
        if ( v685 < v681 )
        {
          v700 = v683 + 1;
          do
          {
            v701 = v700++;
            *(_QWORD *)(v680 + 8 * v685++) = &v677[14 * v701];
          }
          while ( v685 < v681 );
        }
        Table = (*(__int64 (__fastcall **)(__int64 **, _QWORD, _QWORD, _QWORD, __int64))(v686 + 64))(
                  v679,
                  v678,
                  *((_QWORD *)v791 + 2),
                  (unsigned int)v681,
                  v680);
        sqlite3VtabImportErrmsg(a1, v684);
        LODWORD(v7) = Table;
        if ( Table )
          goto LABEL_1840;
        nn = (*(__int64 (__fastcall **)(__int64 **))(v686 + 80))(v679);
        *(_BYTE *)(v676 + 2) = 0;
        if ( (_DWORD)nn )
        {
          v7 = 0;
          v6 = a1;
          v17 = v791;
          v5 = v794;
          v14 = v793;
          goto LABEL_423;
        }
        v2 = v796;
        v3 = 0;
        v6 = a1;
        goto LABEL_67;
      case 7:
        v879 = 0;
        if ( *(_BYTE *)(v2 + 103) )
          goto LABEL_82;
        nn = *((_QWORD *)v17 + 2);
        v719 = *(__int64 **)(nn + 16);
        if ( !v719 )
          goto LABEL_1889;
        v720 = *v719;
        if ( !*v719 )
          goto LABEL_1889;
        v721 = *((int *)v17 + 2);
        if ( !*(_QWORD *)(v720 + 104) )
        {
          v9 = v788;
          v12 = 0x180000000uLL;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v722 = *(_BYTE *)(v2 + 108);
        v723 = v6[14];
        v724 = 0;
        v725 = v5 + 56LL * *((int *)v17 + 3);
        if ( (int)v721 > 0 )
        {
          do
          {
            *(_QWORD *)(v723 + 8 * v724) = v725;
            v725 += 56LL;
            ++v724;
          }
          while ( v724 < v721 );
        }
        *(_BYTE *)(v2 + 108) = v17[2];
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, __int64 *))(v720 + 104))(
                  v719,
                  v721,
                  v723,
                  &v879);
        *(_BYTE *)(v2 + 108) = v722;
        nn = sqlite3VtabImportErrmsg(v6, v719);
        v7 = Table;
        if ( Table )
        {
          if ( (_BYTE)Table == 19 )
          {
            nn = *((_QWORD *)v17 + 2);
            if ( *(_BYTE *)(nn + 28) )
            {
              v726 = *((unsigned __int16 *)v17 + 1);
              if ( v726 != 4 )
              {
                v778 = *((_WORD *)v17 + 1);
                if ( v726 == 5 )
                  v778 = 2;
                *((_BYTE *)v6 + 196) = v778;
                goto LABEL_289;
              }
              v5 = v794;
              v3 = 0;
              v9 = v788;
              v7 = 0;
              Table = 0;
              goto LABEL_164;
            }
          }
        }
        else if ( *((_DWORD *)v17 + 1) != Table )
        {
          nn = v879;
          *(_QWORD *)(v2 + 56) = v879;
        }
        ++v6[7];
        if ( Table )
          goto LABEL_289;
        v5 = v794;
        v3 = 0;
        v9 = v788;
        goto LABEL_164;
      case 8:
      case 184:
        if ( (*(_BYTE *)(v2 + 110) & 1) != 0 && *((_BYTE *)v6 + 197) != 0xFE )
        {
          v763 = (const char *)*((_QWORD *)v17 + 2);
          if ( v763 || (v763 = (const char *)v6[31]) != 0 )
          {
            if ( *(int *)(v2 + 228) <= 1 )
            {
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(v2 + 248))(1, *(_QWORD *)(v2 + 256), v6);
            }
            else
            {
              v764 = sqlite3MPrintf(v2, "-- %s", v763);
              (*(void (__fastcall **)(__int64, _QWORD, __int64 *, __int64))(v2 + 248))(
                1,
                *(_QWORD *)(v2 + 256),
                v6,
                v764);
              if ( v764 )
                sqlite3DbFreeNN(v2);
            }
            v7 = Table;
            v12 = 0x180000000uLL;
            v5 = v794;
            v9 = v788;
            v8 = v792;
          }
          else
          {
            v7 = Table;
          }
        }
        nn = *((unsigned int *)v17 + 1);
        if ( (int)nn < dword_180337B68 )
          goto LABEL_1821;
        if ( *v17 == 0xB8 )
          goto LABEL_167;
        v765 = 1;
        if ( *((int *)v6 + 36) > 1 )
        {
          v766 = 24;
          do
          {
            v767 = v6[17];
            if ( *(_BYTE *)(v766 + v767) == 15 )
              *(_DWORD *)(v766 + v767 + 4) = 0;
            ++v765;
            v766 += 24;
          }
          while ( v765 < *((_DWORD *)v6 + 36) );
        }
        LODWORD(nn) = 0;
LABEL_1821:
        *((_DWORD *)v17 + 1) = nn + 1;
        ++*((_DWORD *)v6 + 59);
        goto LABEL_423;
      case 9:
        goto LABEL_1706;
      case 10:
        v8 = 56LL * *((int *)v17 + 1);
        *(_WORD *)(v8 + v5 + 20) = 4;
        v21 = (__int64)((unsigned __int128)((__int64)&v17[-v14] * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 2;
        *(_QWORD *)(v8 + v5) = (int)(v21 + (v21 >> 63));
        goto LABEL_1706;
      case 11:
        v22 = 56LL * *((int *)v17 + 1);
        nn = *((_DWORD *)v17 + 3) - 1;
        *(_QWORD *)(v22 + v5) = nn;
        *(_WORD *)(v22 + v5 + 20) = 4;
        if ( *((_DWORD *)v17 + 2) )
          goto LABEL_423;
        v10 = v805;
        v17 += 24;
        continue;
      case 12:
        v25 = 56LL * *((int *)v17 + 1);
        *(_WORD *)(v25 + v5 + 20) = 4;
        v26 = (__int64)((unsigned __int128)((__int64)&v17[-v14] * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 2;
        nn = (int)(v26 + (v26 >> 63));
        v17 = (unsigned __int8 *)(v14 + 24LL * *(int *)(v25 + v5));
        *(_QWORD *)(v25 + v5) = nn;
        goto LABEL_165;
      case 13:
        v109 = *((int *)v17 + 1);
        v110 = v5 + 56 * v109;
        v111 = *(_WORD *)(v110 + 20);
        if ( (v111 & 4) != 0 )
          goto LABEL_293;
        if ( (v111 & 0x28) != 0 )
        {
          sqlite3VdbeIntegerAffinity(v5 + 56 * v109, 0x180000000uLL, v8, v7);
        }
        else
        {
          if ( (v111 & 2) == 0 )
            goto LABEL_285;
          applyNumericAffinity(v5 + 56 * v109, 1, v8, v7);
          v7 = Table;
          v5 = v794;
          v9 = v788;
        }
        v8 = v792;
        v12 = 0x180000000uLL;
LABEL_285:
        v111 = *(_WORD *)(v110 + 20);
        if ( (v111 & 4) != 0 )
        {
LABEL_293:
          nn = 62020;
          *(_WORD *)(v110 + 20) = v111 & 0xF240 | 4;
          v10 = v805;
          v17 += 24;
          continue;
        }
        if ( *((_DWORD *)v17 + 2) )
          goto LABEL_423;
        LODWORD(v7) = 20;
        goto LABEL_288;
      case 14:
        if ( (int)v8 >= 0 )
        {
          if ( (_DWORD)v8 )
            nn = *((_DWORD *)v17 + 3) - 1;
          else
            nn = *((_DWORD *)v17 + 2) - 1;
          v10 = v805;
          v17 = (unsigned __int8 *)(v14 + 24 * nn + 24);
        }
        else
        {
          nn = *((_DWORD *)v17 + 1) - 1;
          v10 = v805;
          v17 = (unsigned __int8 *)(v14 + 24 * nn + 24);
        }
        continue;
      case 15:
        v155 = v6[33];
        if ( v155 )
        {
          v156 = *(_QWORD *)(v155 + 40);
          v157 = (((int)v17 - *((_DWORD *)v6 + 34)) / 24) & 7;
          v158 = (unsigned __int64)(unsigned int)(((int)v17 - *((_DWORD *)v6 + 34)) / 24) >> 3;
          v159 = *(unsigned __int8 *)(v158 + v156);
          if ( _bittest(&v159, v157) )
            goto LABEL_422;
          *(_BYTE *)(v158 + v156) = v159 | (1 << v157);
          v12 = 0x180000000uLL;
          v7 = Table;
        }
        else if ( *(_DWORD *)(v6[17] + 4) == *((_DWORD *)v17 + 1) )
        {
          goto LABEL_423;
        }
        nn = v6[17];
        v8 = v792;
        *((_DWORD *)v17 + 1) = *(_DWORD *)(nn + 4);
        v10 = v805;
        v17 += 24;
        continue;
      case 16:
        nn = sqlite3VdbeBooleanValue(v5 + 56LL * *((int *)v17 + 1), *((unsigned int *)v17 + 3), v8, v17);
        if ( (_DWORD)nn )
          goto LABEL_421;
        goto LABEL_129;
      case 17:
        nn = sqlite3VdbeBooleanValue(v5 + 56LL * *((int *)v17 + 1), *((_DWORD *)v17 + 3) == 0, v8, v7);
        if ( !(_DWORD)nn )
          goto LABEL_421;
        goto LABEL_129;
      case 18:
        v160 = *((int *)v17 + 1);
        if ( (int)v160 < 0 )
        {
          LOBYTE(v164) = *((_BYTE *)qword_18026F2C0 + (*(_WORD *)(56LL * *((int *)v17 + 3) + v5 + 20) & 0x3F));
        }
        else
        {
          v161 = *(_QWORD *)(v6[15] + 8 * v160);
          v162 = *((int *)v17 + 3);
          if ( (int)v162 < *(unsigned __int16 *)(v161 + 74) )
          {
            v163 = *(unsigned int *)(v161 + 4 * v162 + 120);
            v12 = 0x180000000uLL;
            if ( (unsigned int)v163 < 0xC )
            {
              nn = *((unsigned __int8 *)&qword_18026F3A0[2] + v163);
            }
            else
            {
              nn = 4;
              if ( (v163 & 1) == 0 )
                LOWORD(nn) = 8;
            }
LABEL_438:
            if ( ((unsigned __int16)nn & *((_WORD *)v17 + 1)) == 0 )
            {
              v10 = v805;
              v17 += 24;
              continue;
            }
            goto LABEL_423;
          }
          v12 = 0x180000000uLL;
          v164 = *((_DWORD *)v17 + 4);
        }
        nn = 1;
        LOWORD(nn) = 1 << (v164 - 1);
        goto LABEL_438;
      case 19:
        v150 = v5 + 56LL * *((int *)v17 + 1);
        v151 = v5 + 56LL * *((int *)v17 + 2);
        v152 = *(_WORD *)(v150 + 20);
        if ( (v152 & 1) != 0 )
        {
          nn = 36864;
          if ( (*(_WORD *)(v151 + 20) & 0x9000) != 0 )
            goto LABEL_408;
          *(_WORD *)(v151 + 20) = 1;
          v10 = v805;
          v17 += 24;
          continue;
        }
        if ( (v152 & 0x24) != 0 )
        {
          nn = *(_QWORD *)(v5 + 56LL * *((int *)v17 + 1)) == 0;
LABEL_404:
          if ( (*(_WORD *)(v151 + 20) & 0x9000) != 0 )
          {
            nn = vdbeReleaseAndSetInt64(v151, nn, v8, v7);
            goto LABEL_129;
          }
          *(_QWORD *)v151 = nn;
          *(_WORD *)(v151 + 20) = 4;
          v10 = v805;
          v17 += 24;
          continue;
        }
        if ( (v152 & 8) != 0 )
        {
          _XMM0.m128i_i64[0] = *(_QWORD *)v150;
        }
        else
        {
          if ( (v152 & 0x12) == 0 )
            goto LABEL_403;
          memRealValue(v150, 0x180000000uLL, v8, v7);
          v7 = Table;
          v12 = 0x180000000uLL;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        if ( *(double *)_XMM0.m128i_i64 != 0.0 )
        {
          nn = 0;
          goto LABEL_404;
        }
LABEL_403:
        nn = 1;
        goto LABEL_404;
      case 20:
        nn = v6[15];
        v165 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        if ( !v165 || !*(_BYTE *)(v165 + 2) )
          goto LABEL_24;
        v166 = v5 + 56LL * *((int *)v17 + 3);
        if ( (*(_WORD *)(v166 + 20) & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 3), v165, v8);
LABEL_421:
          v5 = v794;
LABEL_422:
          v7 = Table;
        }
        else
        {
          *(_WORD *)(v166 + 20) = 1;
        }
        goto LABEL_423;
      case 21:
      case 22:
      case 23:
      case 24:
        v342 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        *(_BYTE *)(v342 + 2) = 0;
        *(_BYTE *)(v342 + 3) = 0;
        *(_DWORD *)(v342 + 32) = 0;
        if ( *(_BYTE *)(v342 + 4) )
        {
          v343 = v5 + 56LL * *((int *)v17 + 3);
          v344 = *(_WORD *)(v343 + 20);
          if ( (v344 & 0x2E) == 2 )
            applyNumericAffinity(v5 + 56LL * *((int *)v17 + 3), 0, v8, v17);
          v345 = sqlite3_value_int64(v343, v12, v8);
          v346 = *(_WORD *)(v343 + 20);
          v347 = v345;
          *(_WORD *)(v343 + 20) = v344;
          if ( (v346 & 0x24) == 0 )
          {
            if ( (v346 & 8) == 0 )
            {
              if ( (v346 & 1) != 0 || (unsigned int)v18 >= 0x17 )
              {
LABEL_1678:
                v7 = Table;
                v17 = v791;
                v5 = v794;
                v14 = v793;
                goto LABEL_423;
              }
              v348 = *(_BYTE **)(v342 + 48);
              if ( !*v348 && (v348[1] & 8) != 0 )
              {
                nn = 0;
                v799 = 0;
                v7 = 0;
                Table = 0;
                goto LABEL_931;
              }
              nn = btreeLast(v348, &v799);
              Table = nn;
              v7 = (unsigned int)nn;
              if ( !(_DWORD)nn )
              {
LABEL_931:
                if ( !v799 )
                  goto LABEL_938;
LABEL_925:
                v17 = v791;
LABEL_926:
                v5 = v794;
                v14 = v793;
                goto LABEL_423;
              }
LABEL_1046:
              v2 = v796;
              goto LABEL_289;
            }
            v349 = sqlite3IntFloatCompare(v345);
            if ( v349 <= 0 )
            {
              if ( v349 < 0 && (v18 & 1) != 0 )
                LODWORD(v18) = v18 + 1;
            }
            else if ( (v18 & 1) == 0 )
            {
              LODWORD(v18) = v18 - 1;
            }
          }
          v350 = (__int64 *)(v342 + 48);
          v351 = sqlite3BtreeTableMoveto(*(_QWORD *)(v342 + 48), v347, 0, &v799);
          *(_QWORD *)(v342 + 80) = v347;
          v7 = v351;
          Table = v351;
          if ( v351 )
          {
LABEL_1930:
            v2 = v796;
            goto LABEL_289;
          }
        }
        else
        {
          v350 = (__int64 *)(v342 + 48);
          v353 = *((_DWORD *)v17 + 4);
          v354 = *(_BYTE *)(*(_QWORD *)(v342 + 48) + 3LL) & 2;
          v863[0] = *(_QWORD *)(v342 + 56);
          v864 = v353;
          LODWORD(v3) = v354 != 0;
          v355 = 1;
          if ( (((_BYTE)v18 - 1) & 1) != 0 )
            v355 = -1;
          v865 = v355;
          v356 = *((int *)v17 + 3);
          v866 = 0;
          v863[1] = v5 + 56 * v356;
          nn = sqlite3BtreeIndexMoveto(*v350, v863, &v799);
          Table = nn;
          v7 = (unsigned int)nn;
          if ( (_DWORD)nn )
            goto LABEL_1930;
          if ( v354 && !v866 )
            goto LABEL_931;
        }
        nn = v799;
        if ( (int)v18 < 23 )
        {
          if ( v799 <= 0 && (v799 || (_DWORD)v18 != 21) )
          {
            nn = *v350;
            v799 = *(_BYTE *)*v350 != 0;
            goto LABEL_931;
          }
          v361 = *v350;
          v799 = 0;
          *(_BYTE *)(v361 + 1) &= 0xF1u;
          *(_WORD *)(v361 + 70) = 0;
          if ( *(_BYTE *)v361
            || (v352 = *(unsigned __int16 *)(v361 + 86), !(_WORD)v352)
            || (nn = *(_QWORD *)(v361 + 136), !*(_BYTE *)(nn + 8)) )
          {
            nn = btreePrevious(v361, v352, v8, v7);
            Table = nn;
            v7 = (unsigned int)nn;
            if ( !(_DWORD)nn )
              goto LABEL_938;
            v360 = (_DWORD)nn == 101;
LABEL_923:
            if ( v360 )
            {
              v7 = 0;
              Table = 0;
              v799 = 1;
              goto LABEL_925;
            }
            goto LABEL_1930;
          }
          *(_WORD *)(v361 + 86) = v352 - 1;
        }
        else
        {
          if ( v799 >= 0 && (v799 || (_DWORD)v18 != 24) )
          {
            v799 = 0;
LABEL_938:
            v2 = v796;
            v5 = v794;
            if ( (_DWORD)v3 )
              v791 += 24;
            v17 = v791;
            v3 = 0;
            v9 = v788;
            goto LABEL_164;
          }
          v357 = *v350;
          v799 = 0;
          *(_WORD *)(v357 + 70) = 0;
          *(_BYTE *)(v357 + 1) &= 0xF9u;
          if ( *(_BYTE *)v357 )
          {
            nn = btreeNext(v357, v352, v8, v7);
LABEL_921:
            Table = nn;
            v7 = (unsigned int)nn;
            if ( !(_DWORD)nn )
              goto LABEL_938;
            v360 = (_DWORD)nn == 101;
            goto LABEL_923;
          }
          v358 = *(unsigned __int16 *)(v357 + 86);
          v359 = *(_QWORD *)(v357 + 136);
          nn = (unsigned int)(v358 + 1);
          *(_WORD *)(v357 + 86) = v358 + 1;
          if ( (unsigned __int16)(v358 + 1) >= *(_WORD *)(v359 + 24) )
          {
            *(_WORD *)(v357 + 86) = v358;
            nn = btreeNext(v357, v359, v358, v7);
            goto LABEL_921;
          }
          if ( !*(_BYTE *)(v359 + 8) )
          {
            nn = moveToLeftmost(v357);
            goto LABEL_921;
          }
        }
        v7 = 0;
        Table = 0;
        goto LABEL_938;
      case 25:
        nn = v6[15];
        v378 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        if ( !v378 || *(_BYTE *)(v378 + 2) )
          goto LABEL_1706;
        goto LABEL_24;
      case 26:
        nn = *(unsigned __int16 *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 12LL);
        if ( (int)nn < *((_DWORD *)v17 + 4) )
          goto LABEL_980;
        goto LABEL_167;
      case 27:
      case 28:
      case 29:
LABEL_980:
        v379 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v380 = v5 + 56LL * *((int *)v17 + 3);
        v835 = v380;
        v836 = *((_WORD *)v17 + 8);
        if ( v836 )
        {
          v381 = (int *)(v379 + 36);
          v834 = *(_QWORD *)(v379 + 56);
          v837 = 0;
          v382 = sqlite3BtreeIndexMoveto(*(_QWORD *)(v379 + 48), &v834, v379 + 36);
          v7 = v382;
          Table = v382;
        }
        else
        {
          if ( (*(_WORD *)(v380 + 20) & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v380, 0x180000000uLL, v8) )
            goto LABEL_82;
          v383 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v379 + 56), v12, v8);
          v384 = v383;
          if ( !v383 )
            goto LABEL_82;
          sqlite3VdbeRecordUnpack(*(_QWORD *)(v379 + 56), *(unsigned int *)(v835 + 16), *(_QWORD *)(v835 + 8), v383);
          *(_BYTE *)(v384 + 30) = 0;
          v381 = (int *)(v379 + 36);
          Table = sqlite3BtreeIndexMoveto(*(_QWORD *)(v379 + 48), v384, v379 + 36);
          sqlite3DbFreeNN(v2);
          v7 = Table;
          v3 = 0;
          v14 = v793;
        }
        if ( (_DWORD)v7 )
          goto LABEL_289;
        v385 = *v381;
        *(_BYTE *)(v379 + 2) = *v381 != 0;
        *(_BYTE *)(v379 + 3) = 0;
        *(_DWORD *)(v379 + 32) = 0;
        nn = *v17;
        if ( (_BYTE)nn == 29 )
        {
          if ( v385 )
          {
            v5 = v794;
            v9 = v788;
            goto LABEL_165;
          }
        }
        else if ( !v385 )
        {
          if ( (_BYTE)nn != 27 )
          {
            v5 = v794;
            if ( *v17 == 26 )
            {
              nn = *((unsigned __int16 *)v17 + 8);
              v9 = v788;
              *(_WORD *)(v379 + 12) = nn;
              goto LABEL_165;
            }
            goto LABEL_1124;
          }
          v386 = 0;
          if ( !v836 )
          {
LABEL_1122:
            v17 = v791;
LABEL_1123:
            v5 = v794;
            goto LABEL_1124;
          }
          nn = v835 + 20;
          while ( (*(_BYTE *)nn & 1) == 0 )
          {
            ++v386;
            nn += 56;
            if ( v386 >= v836 )
            {
              v5 = v794;
              v9 = v788;
              goto LABEL_165;
            }
          }
        }
        goto LABEL_925;
      case 30:
        v387 = 56LL * *((int *)v17 + 3);
        if ( (*(_BYTE *)(v387 + v5 + 20) & 0x24) != 0 )
          goto LABEL_1007;
        v880 = *(_OWORD *)(v387 + v5);
        v881 = *(_OWORD *)(v387 + v5 + 16);
        _XMM0 = *(__m128i *)(v387 + v5 + 32);
        v882 = _XMM0;
        v883 = *(_QWORD *)(v387 + v5 + 48);
        if ( (BYTE4(v881) & 4) == 0 )
        {
          if ( (BYTE4(v881) & 0x28) != 0 )
          {
            sqlite3VdbeIntegerAffinity(&v880, 0x180000000uLL, v8, v7);
          }
          else if ( (BYTE4(v881) & 2) != 0 )
          {
            applyNumericAffinity(&v880, 1, v8, v7);
            v7 = Table;
            v5 = v794;
          }
        }
        if ( (BYTE4(v881) & 4) == 0 )
          goto LABEL_423;
        v388 = v880;
LABEL_1008:
        LODWORD(v875) = 0;
        v389 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v390 = sqlite3BtreeTableMoveto(*(_QWORD *)(v389 + 48), v388, 0, &v875);
        *(_QWORD *)(v389 + 80) = v388;
        v7 = v390;
        *(_BYTE *)(v389 + 2) = 0;
        *(_DWORD *)(v389 + 32) = 0;
        Table = v390;
        nn = (unsigned int)v875;
        *(_BYTE *)(v389 + 3) = 0;
        *(_DWORD *)(v389 + 36) = nn;
        if ( !(_DWORD)nn )
          goto LABEL_845;
        if ( !*((_DWORD *)v17 + 2) )
        {
          sqlite3_log(
            11,
            "%s at line %d of [%.10s]",
            "database corruption",
            98840,
            "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
          LODWORD(v7) = 11;
          Table = 11;
          goto LABEL_289;
        }
        v5 = v794;
        v14 = v793;
        goto LABEL_423;
      case 31:
LABEL_1007:
        v388 = *(_QWORD *)(56LL * *((int *)v17 + 3) + v5);
        goto LABEL_1008;
      case 32:
      case 137:
        v449 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        nn = 0;
        LODWORD(v875) = 0;
        v450 = *(_BYTE **)(v449 + 48);
        if ( (_BYTE)v18 == 0x89 )
        {
          *(_DWORD *)(v449 + 36) = -1;
          if ( !*v450 )
            goto LABEL_1663;
        }
        else if ( !*v450 && (v450[1] & 8) != 0 )
        {
          *(_BYTE *)(v449 + 2) = 0;
          v7 = 0;
          *(_BYTE *)(v449 + 3) = 0;
          *(_DWORD *)(v449 + 32) = 0;
          Table = 0;
          goto LABEL_1155;
        }
        v451 = btreeLast(v450, &v875);
        v7 = v451;
        Table = v451;
        nn = (unsigned int)v875;
        *(_WORD *)(v449 + 2) = (unsigned __int8)v875;
        *(_DWORD *)(v449 + 32) = 0;
        if ( (_DWORD)v7 )
          goto LABEL_289;
        v5 = v794;
        v12 = 0x180000000uLL;
        v9 = v788;
        v8 = v792;
LABEL_1155:
        if ( *((int *)v17 + 2) <= 0 )
          goto LABEL_1191;
        if ( (_DWORD)nn )
          goto LABEL_926;
        v14 = v793;
        v10 = v805;
        v17 += 24;
        continue;
      case 33:
        v452 = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL);
        v453 = moveToRoot(v452, 0x180000000uLL, v8, v7);
        Table = v453;
        v7 = v453;
        if ( v453 )
        {
          if ( v453 == 16 )
          {
            v7 = 0;
            Table = 0;
            v456 = -1;
            goto LABEL_1170;
          }
          v454 = v806;
        }
        else
        {
          v454 = 0;
          v455 = moveToLeftmost(v452);
          v7 = v455;
          Table = v455;
        }
        if ( (_DWORD)v7 )
          goto LABEL_289;
        Table = 0;
        if ( v454 )
        {
          v456 = -1;
        }
        else
        {
          v457 = sqlite3BtreeRowCountEst(v452);
          v456 = (__int16)sqlite3LogEst(v457);
          v7 = v458;
          Table = v458;
        }
LABEL_1170:
        nn = *((int *)v17 + 3);
        if ( v456 >= nn )
        {
          nn = *((int *)v17 + 4);
          if ( v456 <= nn )
          {
            v5 = v794;
            v806 = 1;
            goto LABEL_423;
          }
        }
        v5 = v794;
        v9 = v788;
        v806 = 0;
        goto LABEL_165;
      case 34:
      case 35:
        ++*((_DWORD *)v6 + 55);
        goto LABEL_1175;
      case 36:
LABEL_1175:
        v459 = 1;
        nn = v6[15];
        v460 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        v461 = *(_QWORD *)(v460 + 48);
        if ( *(_BYTE *)v460 == 1 )
        {
          Table = 0;
          if ( !*(_BYTE *)(v461 + 88) )
          {
            if ( *(_QWORD *)(v461 + 56) )
            {
              v459 = 0;
              nn = vdbeSorterSort(v461 + 96, v461 + 56, 0, v7);
              Table = nn;
            }
            goto LABEL_1179;
          }
          v462 = vdbeSorterFlushPMA(v461, 0x180000000uLL, v8, v7);
          nn = vdbeSorterJoinAll(v461, v462);
          Table = nn;
          if ( (_DWORD)nn )
          {
LABEL_1179:
            v3 = 0;
            goto LABEL_1187;
          }
          nn = vdbeSorterSetupMerge(v461);
          v3 = 0;
          Table = nn;
          v459 = 0;
        }
        else
        {
          nn = moveToRoot(*(_QWORD *)(v460 + 48), 0x180000000uLL, v8, v7);
          Table = nn;
          if ( (_DWORD)nn )
          {
            if ( (_DWORD)nn == 16 )
            {
              v8 = 0;
              Table = 0;
            }
          }
          else
          {
            v459 = 0;
            nn = moveToLeftmost(v461);
            Table = nn;
          }
          v3 = 0;
          *(_BYTE *)(v460 + 3) = 0;
          *(_DWORD *)(v460 + 32) = 0;
        }
LABEL_1187:
        v7 = Table;
        if ( Table )
          goto LABEL_289;
        *(_BYTE *)(v460 + 2) = v459;
        if ( *((_DWORD *)v17 + 2) <= (signed int)Table )
        {
LABEL_1191:
          v14 = v793;
          v5 = v794;
          v9 = v788;
          goto LABEL_165;
        }
        if ( !v459 )
          goto LABEL_69;
        v5 = v794;
        v14 = v793;
        goto LABEL_423;
      case 37:
        v463 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v464 = *(_QWORD *)(v463 + 48);
        if ( *(_BYTE *)(v464 + 88) )
        {
          if ( *(_BYTE *)(v464 + 89) )
          {
            Table = vdbePmaReaderNext(*(_QWORD *)(v464 + 16), 0x180000000uLL, v8, v7);
            if ( !Table && !*(_QWORD *)(*(_QWORD *)(v464 + 16) + 24LL) )
            {
              v465 = v17;
              v14 = v793;
              Table = 101;
              goto LABEL_1219;
            }
          }
          else
          {
            v466 = *(_QWORD *)(v464 + 24);
            LODWORD(v875) = 0;
            Table = vdbeMergeEngineStep(v466, &v875, v8, v7);
            if ( !Table && (_DWORD)v875 )
            {
              v465 = v17;
              v14 = v793;
              Table = 101;
              goto LABEL_1219;
            }
          }
        }
        else
        {
          v467 = *(_QWORD *)(v464 + 56);
          *(_QWORD *)(v464 + 56) = *(_QWORD *)(v467 + 8);
          *(_QWORD *)(v467 + 8) = 0;
          if ( !*(_QWORD *)(v464 + 64) )
          {
            do
            {
              v468 = *(_QWORD *)(v467 + 8);
              sqlite3DbFreeNN(v2);
              v467 = v468;
            }
            while ( v468 );
          }
          v469 = 101;
          v8 = 0;
          if ( *(_QWORD *)(v464 + 56) )
            v469 = 0;
          Table = v469;
        }
        v465 = v17;
        v14 = v793;
        goto LABEL_1219;
      case 38:
        v465 = v17;
        v463 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v470 = *(_QWORD *)(v463 + 48);
        *(_BYTE *)(v470 + 1) &= 0xF1u;
        *(_WORD *)(v470 + 70) = 0;
        if ( !*(_BYTE *)v470 )
        {
          v12 = *(unsigned __int16 *)(v470 + 86);
          if ( (_WORD)v12 )
          {
            if ( *(_BYTE *)(*(_QWORD *)(v470 + 136) + 8LL) )
            {
              Table = 0;
              *(_WORD *)(v470 + 86) = v12 - 1;
              goto LABEL_1219;
            }
          }
        }
        v471 = btreePrevious(v470, v12, v8, v7);
        goto LABEL_1218;
      case 39:
        v465 = v17;
        v463 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v472 = *(_QWORD *)(v463 + 48);
        *(_WORD *)(v472 + 70) = 0;
        *(_BYTE *)(v472 + 1) &= 0xF9u;
        if ( *(_BYTE *)v472 )
        {
          v471 = btreeNext(v472, 0x180000000uLL, v8, v7);
        }
        else
        {
          v8 = *(unsigned __int16 *)(v472 + 86);
          v473 = *(_QWORD *)(v472 + 136);
          *(_WORD *)(v472 + 86) = v8 + 1;
          if ( (unsigned __int16)(v8 + 1) < *(_WORD *)(v473 + 24) )
          {
            if ( *(_BYTE *)(v473 + 8) )
            {
              Table = 0;
              goto LABEL_1219;
            }
            v471 = moveToLeftmost(v472);
          }
          else
          {
            *(_WORD *)(v472 + 86) = v8;
            v471 = btreeNext(v472, v473, v8, v7);
          }
        }
LABEL_1218:
        Table = v471;
LABEL_1219:
        LODWORD(v7) = Table;
        *(_DWORD *)(v463 + 32) = 0;
        if ( Table )
        {
          if ( Table != 101 )
            goto LABEL_289;
          Table = 0;
          *(_BYTE *)(v463 + 2) = 1;
        }
        else
        {
          *(_BYTE *)(v463 + 2) = 0;
          ++*((_DWORD *)v6 + *((unsigned __int16 *)v465 + 1) + 53);
LABEL_1706:
          v791 = (unsigned __int8 *)(v14 + 24LL * (*((_DWORD *)v17 + 2) - 1));
        }
        goto LABEL_1361;
      case 40:
      case 41:
      case 42:
      case 45:
        v493 = (unsigned __int8)v18 < 0x2Au;
        v494 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v495 = *(_QWORD *)(v494 + 48);
        v813[0] = *(_QWORD *)(v494 + 56);
        v814 = *((_WORD *)v17 + 8);
        v815 = -v493;
        v813[1] = v5 + 56LL * *((int *)v17 + 3);
        getCellInfo(v495, v494, v8);
        v496 = *(_DWORD *)(v495 + 64);
        if ( v496 - 1 > 0x7FFFFFFE )
        {
          LODWORD(v7) = sqlite3CorruptError(100137);
          Table = v7;
          goto LABEL_289;
        }
        v847 = 0;
        v848 = v2;
        v849 = 0;
        v497 = *(unsigned __int16 *)(v495 + 68);
        v498 = *(_DWORD *)(*(_QWORD *)(v495 + 136) + 88LL) - *(_DWORD *)(v495 + 56);
        if ( v497 > v498 )
        {
          v497 = *(_DWORD *)(*(_QWORD *)(v495 + 136) + 88LL) - *(_DWORD *)(v495 + 56);
          if ( v498 < 0 )
            v497 = 0;
        }
        v499 = *(_QWORD *)(v495 + 56);
        v845 = v499;
        if ( v496 > v497 )
        {
          _mm_lfence();
          Table = sqlite3VdbeMemFromBtree(v495, 0, v496, v844);
          LODWORD(v7) = Table;
          if ( Table )
            goto LABEL_289;
          v496 = v846;
          v499 = v845;
        }
        else
        {
          Table = 0;
          v847 = 16400;
          v3 = 0;
          v846 = v496;
        }
        nn = sqlite3VdbeRecordCompareWithSkip(v496, v499, v813, 0);
        v500 = nn;
        if ( v849 )
          nn = vdbeMemClear(v844);
        if ( (*v17 & 1) != 0 )
          v501 = v500 + 1;
        else
          v501 = -v500;
        v7 = 0;
        if ( v501 > 0 )
          goto LABEL_926;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 43:
      case 44:
        v137 = v17;
        v138 = v5 + 56LL * *((int *)v17 + 1);
        v139 = *(_WORD *)(v138 + 20);
        if ( (v139 & 0x24) != 0 )
        {
          v140 = *(_QWORD *)(v5 + 56LL * *((int *)v17 + 1)) != 0;
          goto LABEL_385;
        }
        if ( (v139 & 1) != 0 )
        {
          v140 = 2;
          goto LABEL_385;
        }
        if ( (v139 & 8) != 0 )
        {
          _XMM0.m128i_i64[0] = *(_QWORD *)v138;
        }
        else
        {
          if ( (v139 & 0x12) == 0 )
            goto LABEL_384;
          memRealValue(v138, 0x180000000uLL, v8, v17);
          v137 = v17;
          v5 = v794;
        }
        if ( *(double *)_XMM0.m128i_i64 != 0.0 )
        {
          v140 = 1;
          goto LABEL_385;
        }
LABEL_384:
        v140 = 0;
LABEL_385:
        v141 = sqlite3VdbeBooleanValue(v5 + 56LL * *((int *)v137 + 2), 2, v8, v137);
        v5 = v794;
        v142 = v141 + 2 * v140 + v140;
        v143 = qword_18026F390;
        if ( *v17 != 44 )
          v143 = qword_18026F3A0;
        v144 = *((unsigned __int8 *)v143 + v142);
        v145 = 56LL * *((int *)v17 + 3);
        if ( (_BYTE)v144 == 2 )
        {
          nn = *(unsigned __int16 *)(v145 + v794 + 20);
          v7 = Table;
          LOWORD(nn) = nn & 0xF240 | 1;
          v9 = v788;
        }
        else
        {
          v7 = Table;
          v9 = v788;
          *(_QWORD *)(v145 + v794) = v144;
          nn = *(unsigned __int16 *)(v145 + v794 + 20);
          LOWORD(nn) = nn & 0xF240 | 4;
        }
        *(_WORD *)(v145 + v794 + 20) = nn;
        goto LABEL_165;
      case 46:
        v550 = v5 + 56LL * *((int *)v17 + 1);
        if ( (*(_BYTE *)(v550 + 20) & 0x10) != 0 )
        {
          v551 = *(_QWORD *)(v550 + 8);
          v552 = *(_WORD *)(v551 + 50);
          if ( (v552 & 2) == 0 )
          {
            if ( (v552 & 1) == 0 )
              *(_QWORD *)(v551 + 16) = rowSetEntrySort(*(_QWORD *)(v551 + 16), 0x180000000uLL, v8, v7);
            *(_WORD *)(v551 + 50) |= 3u;
          }
          v553 = *(__int64 **)(v551 + 16);
          if ( v553 )
          {
            v554 = *v553;
            v555 = v553[1];
            *(_QWORD *)(v551 + 16) = v555;
            if ( !v555 )
              sqlite3RowSetClear(v551, v12, v8, v7);
            v556 = v794 + 56LL * *((int *)v17 + 3);
            if ( (*(_WORD *)(v556 + 20) & 0x9000) != 0 )
            {
              vdbeReleaseAndSetInt64(v794 + 56LL * *((int *)v17 + 3), v554, v8, v7);
            }
            else
            {
              *(_QWORD *)v556 = v554;
              *(_WORD *)(v556 + 20) = 4;
            }
            goto LABEL_1360;
          }
        }
        if ( (*(_WORD *)(v550 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v550, v12, v8);
        else
          *(_WORD *)(v550 + 20) = 1;
LABEL_1705:
        v14 = v793;
        goto LABEL_1706;
      case 47:
        v557 = *((_DWORD *)v17 + 4);
        nn = *((int *)v17 + 3);
        v548 = v5 + 56LL * *((int *)v17 + 1);
        v549 = (_QWORD *)(v5 + 56 * nn);
        if ( (*(_BYTE *)(v548 + 20) & 0x10) == 0 )
        {
          nn = sqlite3VdbeMemSetRowSet(v5 + 56LL * *((int *)v17 + 1), 0x180000000uLL, v8);
          if ( (_DWORD)nn )
            goto LABEL_82;
        }
        v558 = v557 < 0;
        if ( !v557 )
          goto LABEL_1391;
        nn = sqlite3RowSetTest(*(_QWORD *)(v548 + 8), (unsigned int)v557, *v549);
        if ( (_DWORD)nn )
          goto LABEL_1678;
        v558 = v557 < 0;
LABEL_1391:
        if ( !v558 )
          goto LABEL_1392;
        goto LABEL_67;
      case 48:
        v559 = (__int64 *)*((_QWORD *)v17 + 2);
        v560 = v5 + 56LL * *((int *)v17 + 3);
        if ( !*((_WORD *)v791 + 1) )
          goto LABEL_1397;
        nn = v6[33];
        if ( !nn )
          goto LABEL_1397;
        while ( *(_QWORD *)(nn + 48) != v559[4] )
        {
          nn = *(_QWORD *)(nn + 8);
          if ( !nn )
          {
LABEL_1397:
            if ( *((_DWORD *)v6 + 70) >= *(_DWORD *)(v2 + 176) )
            {
              Table = 1;
              sqlite3VdbeError(v6, "too many levels of trigger recursion", v8, v7);
              LODWORD(v7) = 1;
              goto LABEL_289;
            }
            if ( (*(_BYTE *)(v560 + 20) & 0x10) == 0 )
            {
              v561 = *((_DWORD *)v559 + 4);
              v562 = v561 + *((_DWORD *)v559 + 3) + 1;
              if ( v561 )
                v562 = v561 + *((_DWORD *)v559 + 3);
              v563 = (*((_DWORD *)v559 + 2) + 7) / 8 + 8 * (v561 + 7 * (v562 + 2));
              v564 = (_DWORD *)sqlite3DbMallocRawNN(v796, v563);
              v565 = v564;
              if ( v564 )
              {
                memset(v564, 0, v563);
                if ( (*(_WORD *)(v560 + 20) & 0x9000) != 0 || *(_DWORD *)(v560 + 32) )
                  vdbeMemClear(v560);
                *(_WORD *)(v560 + 20) = 4112;
                *(_QWORD *)(v560 + 8) = v565;
                *(_DWORD *)(v560 + 16) = v563;
                v2 = v796;
                *(_QWORD *)(v560 + 48) = sqlite3VdbeFrameMemDel;
                *(_QWORD *)v565 = v6;
                v565[22] = v562;
                v565[23] = *((_DWORD *)v559 + 4);
                v565[19] = (__int64)&v791[-v793] / 24;
                *((_QWORD *)v565 + 3) = v6[13];
                v565[21] = *((_DWORD *)v6 + 9);
                *((_QWORD *)v565 + 4) = v6[15];
                v565[18] = *((_DWORD *)v6 + 10);
                *((_QWORD *)v565 + 2) = v6[17];
                v565[20] = *((_DWORD *)v6 + 36);
                *((_QWORD *)v565 + 6) = v559[4];
                v566 = v565 + 28;
                v567 = &v565[14 * v562 + 28];
                if ( v565 + 28 != v567 )
                {
                  do
                  {
                    *((_WORD *)v566 + 10) = 0;
                    *((_QWORD *)v566 + 3) = v796;
                    v566 += 14;
                  }
                  while ( v566 != v567 );
                }
                goto LABEL_1409;
              }
LABEL_1927:
              v2 = v796;
LABEL_82:
              v11 = v795;
              v4 = (unsigned __int8 *)v793;
LABEL_83:
              sqlite3OomFault(v2);
              sqlite3VdbeError(v6, "out of memory");
              LODWORD(v7) = 7;
LABEL_1325:
              Table = v7;
              goto LABEL_291;
            }
            v565 = *(_DWORD **)(v560 + 8);
LABEL_1409:
            ++*((_DWORD *)v6 + 70);
            *((_QWORD *)v565 + 1) = v6[33];
            *((_QWORD *)v565 + 7) = *(_QWORD *)(v2 + 56);
            *((_QWORD *)v565 + 12) = v6[7];
            v794 = (unsigned __int64)(v565 + 28);
            *((_QWORD *)v565 + 13) = *(_QWORD *)(*v6 + 120);
            *((_QWORD *)v565 + 8) = v6[37];
            v6[37] = 0;
            v6[7] = 0;
            v6[33] = (__int64)v565;
            v6[13] = (__int64)(v565 + 28);
            v568 = (int)v565[22];
            *((_DWORD *)v6 + 9) = v568;
            *((_DWORD *)v6 + 10) = *((unsigned __int16 *)v565 + 46);
            v569 = (__int64)&v565[14 * v568 + 28];
            v6[15] = v569;
            v570 = (void *)(v569 + 8LL * *((int *)v559 + 4));
            *((_QWORD *)v565 + 5) = v570;
            memset(v570, 0, (*((_DWORD *)v559 + 2) + 7) / 8);
            v14 = *v559;
            v6[17] = *v559;
            v793 = v14;
            *((_DWORD *)v6 + 36) = *((_DWORD *)v559 + 2);
            v791 = (unsigned __int8 *)(v14 - 24);
LABEL_1361:
            nn = *(unsigned int *)(v2 + 392);
            if ( !(_DWORD)nn )
            {
              v545 = v795;
              v546 = v805;
              if ( v805 >= v795 )
              {
                do
                {
                  v547 = *(__int64 (__fastcall **)(_QWORD))(v2 + 512);
                  if ( !v547 )
                    goto LABEL_1784;
                  v545 += *(unsigned int *)(v2 + 528);
                  v795 = v545;
                  nn = v547(*(_QWORD *)(v2 + 520));
                  if ( (_DWORD)nn )
                  {
                    LODWORD(v7) = 9;
                    Table = 9;
                    v11 = -1;
                    goto LABEL_290;
                  }
                }
                while ( v546 >= v545 );
                v3 = 0;
                goto LABEL_129;
              }
LABEL_1784:
              v7 = Table;
LABEL_1785:
              v9 = v788;
              v3 = 0;
LABEL_162:
              v17 = v791;
LABEL_163:
              v5 = v794;
              goto LABEL_164;
            }
            v11 = v795;
            v4 = (unsigned __int8 *)v793;
LABEL_1926:
            LODWORD(v7) = 9;
            Table = 9;
            goto LABEL_291;
          }
        }
        v3 = 0;
        v10 = v805;
        v17 = v791 + 24;
        continue;
      case 49:
        if ( *((_DWORD *)v17 + 1) )
        {
          if ( *(_QWORD *)(v2 + 744) )
            goto LABEL_167;
          if ( *(_QWORD *)(v2 + 752) )
          {
            v10 = v805;
            v17 += 24;
            continue;
          }
        }
        else
        {
          if ( v6[10] )
            goto LABEL_167;
          if ( *(_QWORD *)(v2 + 752) )
          {
            v10 = v805;
            v17 += 24;
            continue;
          }
        }
        goto LABEL_423;
      case 50:
        nn = *((int *)v17 + 1);
        if ( (*(_BYTE *)(56 * nn + v5 + 20) & 1) != 0 )
          goto LABEL_423;
        v10 = v805;
        v17 += 24;
        continue;
      case 51:
        nn = *((int *)v17 + 1);
        if ( (*(_BYTE *)(56 * nn + v5 + 20) & 1) == 0 )
          goto LABEL_423;
        v10 = v805;
        v17 += 24;
        continue;
      case 52:
      case 53:
      case 54:
      case 55:
      case 56:
      case 57:
        v114 = (__int64 *)(v5 + 56LL * *((int *)v17 + 1));
        v115 = v5 + 56LL * *((int *)v791 + 3);
        v116 = *((_WORD *)v114 + 10);
        v117 = *(_WORD *)(v115 + 20);
        if ( ((unsigned __int8)v116 & (unsigned __int8)v117 & 4) != 0 )
        {
          v118 = *v114;
          v17 = v791;
          v14 = v793;
          if ( *(_QWORD *)v115 <= v118 )
          {
            if ( *(_QWORD *)v115 >= v118 )
            {
              nn = (__int64)off_180337B80;
              if ( !*((_BYTE *)off_180337B80 + v18) )
              {
                v2 = v796;
                v12 = 0x180000000uLL;
                v8 = 0;
                v792 = 0;
                v10 = v805;
                v17 = v791 + 24;
                continue;
              }
            }
            else
            {
              nn = off_180337B78;
              if ( !*(_BYTE *)(v18 + off_180337B78) )
              {
                v2 = v796;
                v12 = 0x180000000uLL;
                v8 = 0xFFFFFFFFLL;
                v792 = -1;
                v10 = v805;
                v17 = v791 + 24;
                continue;
              }
            }
            goto LABEL_423;
          }
          if ( *((_BYTE *)off_180337B88 + v18) )
            goto LABEL_423;
          nn = 1;
          v8 = 1;
          v792 = 1;
LABEL_308:
          v2 = v796;
          v12 = 0x180000000uLL;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v119 = v117 | v116;
        if ( (((unsigned __int8)v117 | (unsigned __int8)v116) & 1) != 0 )
        {
          v120 = *((_WORD *)v791 + 1);
          if ( (v120 & 0x80u) == 0 )
          {
            v17 = v791;
            v14 = v793;
            if ( (v120 & 0x10) == 0 )
            {
              v2 = v796;
              nn = 1;
              v8 = 1;
              v792 = 1;
              v10 = v805;
              v17 = v791 + 24;
              continue;
            }
            goto LABEL_423;
          }
          if ( ((unsigned __int8)v116 & (unsigned __int8)v117 & 1) != 0 && (v117 & 0x100) == 0 )
          {
            v8 = 0;
            v792 = 0;
            v121 = *v791;
            nn = (__int64)off_180337B80;
            goto LABEL_345;
          }
          v122 = 2 * ((v117 & 1) == 0) - 1;
        }
        else
        {
          v123 = v791[2] & 0x47;
          if ( v123 < 0x43u )
          {
            if ( v123 == 66 && (v119 & 2) != 0 )
            {
              if ( (v116 & 2) != 0 )
              {
                *((_WORD *)v114 + 10) = v116 & 0xFFD3;
              }
              else if ( (v116 & 0x2C) != 0 )
              {
                LOBYTE(v8) = 1;
                sqlite3VdbeMemStringify(v5 + 56LL * *((int *)v791 + 1), v9, v8, v7);
                v9 = v788;
                v116 = *((_WORD *)v114 + 10) ^ (*((_WORD *)v114 + 10) ^ v116) & 0xDBF;
                if ( v114 == (__int64 *)v115 )
                  v117 = v116 | 2;
              }
              if ( (v117 & 2) != 0 )
              {
                *(_WORD *)(v115 + 20) &= 0xFFD3u;
              }
              else if ( (v117 & 0x2C) != 0 )
              {
                LOBYTE(v8) = 1;
                sqlite3VdbeMemStringify(v115, v9, v8, v7);
                v117 = *(_WORD *)(v115 + 20) ^ (*(_WORD *)(v115 + 20) ^ v117) & 0xDBF;
              }
            }
          }
          else if ( (v119 & 2) != 0 )
          {
            if ( (v116 & 0x2E) == 2 )
            {
              applyNumericAffinity(v5 + 56LL * *((int *)v791 + 1), 0, v8, v7);
              v117 = *(_WORD *)(v115 + 20);
            }
            if ( (v117 & 0x2E) == 2 )
              applyNumericAffinity(v115, 0, v8, v7);
          }
          v122 = sqlite3MemCompare(v115, v114, *((_QWORD *)v791 + 2));
          v5 = v794;
          v9 = v788;
        }
        v792 = v122;
        v124 = v122;
        if ( v122 < 0 )
        {
          nn = off_180337B78;
          v8 = v792;
          v125 = *(_BYTE *)(*v791 + off_180337B78);
          goto LABEL_346;
        }
        v121 = *v791;
        v792 = v122;
        if ( v122 )
        {
          nn = (__int64)off_180337B88;
          v8 = v124;
          v792 = v124;
        }
        else
        {
          nn = (__int64)off_180337B80;
          v8 = 0;
        }
LABEL_345:
        v125 = *(_BYTE *)(v121 + nn);
LABEL_346:
        v7 = Table;
        *(_WORD *)(v115 + 20) = v117;
        v14 = v793;
        *((_WORD *)v114 + 10) = v116;
        v17 = v791;
        if ( v125 )
          goto LABEL_423;
        goto LABEL_308;
      case 58:
        if ( !(_DWORD)v8 )
          goto LABEL_423;
        v10 = v805;
        v17 += 24;
        continue;
      case 59:
        nn = *((int *)v17 + 1);
        v581 = *(_QWORD *)(56 * nn + v5);
        if ( v581 <= 0 )
          goto LABEL_166;
        *(_QWORD *)(56 * nn + v5) = v581 - *((int *)v17 + 3);
        goto LABEL_423;
      case 60:
        v588 = 56LL * *((int *)v17 + 1);
        nn = *(_QWORD *)(v588 + v5);
        if ( !nn )
          goto LABEL_71;
        if ( nn > 0 )
          *(_QWORD *)(v588 + v5) = nn - 1;
        goto LABEL_423;
      case 61:
        v589 = 56LL * *((int *)v17 + 1);
        nn = *(_QWORD *)(v589 + v5);
        if ( nn != 0x8000000000000000uLL )
          *(_QWORD *)(v589 + v5) = --nn;
        if ( !nn )
          goto LABEL_423;
        v10 = v805;
        v17 += 24;
        continue;
      case 62:
        v632 = *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 8);
        v633 = *(_QWORD *)(v632 + 8);
        if ( !*(_BYTE *)(v633 + 33) )
          goto LABEL_1595;
        v634 = *(_DWORD *)(v633 + 64);
        v635 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v633 + 24) + 80LL) + 36LL));
        v636 = finalDbSize(*(_QWORD *)(v632 + 8), v634, v635, v7);
        if ( v634 < v636 || v635 >= v634 )
        {
          sqlite3_log(
            11,
            "%s at line %d of [%.10s]",
            "database corruption",
            74921,
            "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
          v2 = v796;
          LODWORD(v7) = 11;
          Table = 11;
          goto LABEL_289;
        }
        if ( !v635 )
          goto LABEL_1594;
        _mm_lfence();
        v637 = *(_QWORD *)(v633 + 16);
        if ( !v637 || (Table = saveCursorsOnList(v637, 0, 0), (v7 = Table) == 0) )
        {
          _mm_lfence();
          for ( m = *(_QWORD *)(v633 + 16); m; m = *(_QWORD *)(m + 40) )
            *(_BYTE *)(m + 1) &= ~4u;
          Table = incrVacuumStep(v633, v636, v634, 0);
          v7 = Table;
          if ( !Table )
          {
            _mm_lfence();
            v640 = sqlite3PagerWrite(*(_QWORD *)(*(_QWORD *)(v633 + 24) + 112LL), v639, v8, (unsigned __int8)Table);
            v7 = v640;
            Table = v640;
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v633 + 24) + 80LL) + 28LL) = _byteswap_ulong(*(_DWORD *)(v633 + 64));
          }
        }
        nn = (unsigned int)v7;
        if ( !(_DWORD)v7 )
        {
          v2 = v796;
          v9 = v788;
          goto LABEL_162;
        }
        Table = v7;
        if ( (_DWORD)v7 != 101 )
          goto LABEL_1046;
LABEL_1594:
        v5 = v794;
LABEL_1595:
        v14 = v793;
        v7 = 0;
        Table = 0;
        goto LABEL_423;
      case 63:
        nn = v6[15];
        v710 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        if ( *(_BYTE *)(v710 + 2) )
          goto LABEL_93;
        v711 = *(__int64 ***)(v710 + 48);
        v712 = *v711;
        v713 = **v711;
        Table = (*(__int64 (__fastcall **)(__int64 **, unsigned __int64, __int64, __int64))(v713 + 72))(
                  v711,
                  0x180000000uLL,
                  v8,
                  v7);
        sqlite3VtabImportErrmsg(v6, v712);
        LODWORD(v7) = Table;
        if ( Table )
          goto LABEL_289;
        if ( !(*(unsigned int (__fastcall **)(_QWORD))(v713 + 80))(*(_QWORD *)(v710 + 48)) )
          goto LABEL_1705;
        goto LABEL_1360;
      case 64:
        v759 = 56LL * *((int *)v17 + 1);
        v760 = filterHash(v5, v17, v8, v7);
        v5 = v794;
        v7 = Table;
        v761 = v760 % (8 * *(_DWORD *)(v759 + v794 + 16));
        v762 = *(char *)((v761 >> 3) + *(_QWORD *)(v759 + v794 + 8));
        nn = v761 & 7;
        if ( !_bittest(&v762, v761 & 7) )
        {
          ++*((_DWORD *)v6 + 61);
          goto LABEL_423;
        }
        ++*((_DWORD *)v6 + 60);
        v9 = v788;
        goto LABEL_165;
      case 65:
      case 66:
        v734 = *((_QWORD *)v17 + 2);
        v735 = *((int *)v791 + 3);
        v801 = v734;
        v736 = v5 + 56 * v735;
        if ( *(_QWORD *)v734 != v736 )
        {
          *(_QWORD *)(v734 + 24) = v6;
          *(_QWORD *)v734 = v736;
          *(_BYTE *)(v734 + 40) = v9;
          v737 = *(unsigned __int8 *)(v734 + 42) - 1LL;
          v738 = *(unsigned __int8 *)(v734 + 42) - 1;
          if ( v737 >= 0 )
          {
            v739 = v734 + 48 + 8 * v737;
            do
            {
              v739 -= 8;
              v740 = v738 + *((_DWORD *)v791 + 2);
              --v738;
              --v737;
              *(_QWORD *)(v739 + 8) = v5 + 56LL * v740;
            }
            while ( v737 >= 0 );
          }
        }
        *(_WORD *)(v736 + 20) &= 0xF241u;
        *(_WORD *)(v736 + 20) |= 1u;
        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)(v734 + 8) + 24LL))(
          v734,
          *(unsigned __int8 *)(v734 + 42),
          v734 + 48);
        nn = *(unsigned int *)(v734 + 36);
        if ( !(_DWORD)nn )
          goto LABEL_1783;
        if ( (int)nn > 0 )
        {
          v741 = *(_WORD *)(v736 + 20);
          v742 = 514;
          if ( (v741 & 0x202) == 0x202 && *(_BYTE *)(v736 + 22) == 1 )
          {
            v743 = *(const char **)(v736 + 8);
          }
          else if ( (v741 & 1) != 0 )
          {
            v743 = 0;
          }
          else
          {
            LOBYTE(v742) = 1;
            v743 = (const char *)valueToText(v736, v742);
          }
          nn = sqlite3VdbeError(v6, "%s", v743);
          Table = *(_DWORD *)(v734 + 36);
          v3 = 0;
        }
        v744 = *((_DWORD *)v791 + 1);
        v745 = v6 + 37;
        v746 = v6[37];
        v747 = *(_DWORD *)(v734 + 32);
        if ( !v746 )
          goto LABEL_1781;
        while ( 1 )
        {
          if ( v747 < 0
            || *(_DWORD *)v746 == v747
            && (nn = *(unsigned int *)(v746 + 4), (int)nn >= 0)
            && ((int)nn > 31 || !_bittest(&v744, nn)) )
          {
            v748 = *(void (__fastcall **)(_QWORD))(v746 + 16);
            if ( v748 )
              v748(*(_QWORD *)(v746 + 8));
            nn = *(_QWORD *)(v746 + 24);
            *v745 = nn;
            if ( !v746 )
              goto LABEL_1779;
            if ( v746 >= *(_QWORD *)(v796 + 480) )
            {
LABEL_1771:
              if ( *(_QWORD *)(v796 + 760) )
              {
                nn = measureAllocationSize(v796, v746);
              }
              else if ( dword_1803379C0 )
              {
                if ( (_QWORD)xmmword_1803DC8D0 )
                  xmmword_180337A40(xmmword_1803DC8D0);
                v749 = (*((__int64 (__fastcall **)(unsigned __int64))&xmmword_1803379F0 + 1))(v746);
                --qword_1803DC858;
                qword_1803DC810 -= v749;
                nn = (*((__int64 (__fastcall **)(unsigned __int64))&xmmword_1803379E0 + 1))(v746);
                if ( (_QWORD)xmmword_1803DC8D0 )
                  nn = xmmword_180337A50(xmmword_1803DC8D0);
              }
              else
              {
                nn = (*((__int64 (__fastcall **)(unsigned __int64))&xmmword_1803379E0 + 1))(v746);
              }
              goto LABEL_1779;
            }
            if ( v746 < *(_QWORD *)(v796 + 464) )
            {
              if ( v746 < *(_QWORD *)(v796 + 472) )
                goto LABEL_1771;
              nn = *(_QWORD *)(v796 + 440);
              *(_QWORD *)v746 = nn;
              *(_QWORD *)(v796 + 440) = v746;
            }
            else
            {
              nn = *(_QWORD *)(v796 + 456);
              *(_QWORD *)v746 = nn;
              *(_QWORD *)(v796 + 456) = v746;
            }
          }
          else
          {
            v745 = (__int64 *)(v746 + 24);
          }
LABEL_1779:
          v746 = *v745;
          if ( !*v745 )
          {
            v734 = v801;
LABEL_1781:
            v7 = Table;
            v2 = v796;
            *(_DWORD *)(v734 + 36) = 0;
            if ( Table )
              goto LABEL_289;
            v17 = v791;
            v5 = v794;
            v9 = v788;
            goto LABEL_164;
          }
        }
      case 67:
        nn = 56LL * *((int *)v17 + 1);
        if ( (*(_BYTE *)(nn + v5 + 20) & 4) == 0 )
          goto LABEL_71;
        nn = *(_QWORD *)(nn + v5);
        v10 = v805;
        v17 = (unsigned __int8 *)(v14 + 24 * nn + 24);
        continue;
      case 68:
        v23 = 56LL * *((int *)v17 + 1);
        v24 = 3LL * *(_QWORD *)(v23 + v5);
        *(_QWORD *)(v23 + v5) = ((int)v17 - *((_DWORD *)v6 + 34)) / 24 - 1;
        nn = *(_DWORD *)(v14 + 8 * v24 + 8) - 1;
        v17 = (unsigned __int8 *)(v14 + 24LL * (int)nn);
        goto LABEL_165;
      case 69:
        nn = *((int *)v17 + 3);
        if ( (*(_BYTE *)(56 * nn + v5 + 20) & 1) != 0 )
          goto LABEL_16;
        goto LABEL_71;
      case 70:
LABEL_16:
        v27 = v6[33];
        if ( v27 && !*((_DWORD *)v17 + 1) )
        {
          v6[33] = *(_QWORD *)(v27 + 8);
          --*((_DWORD *)v6 + 70);
          v28 = v6[7];
          *(_QWORD *)(v2 + 120) = v28;
          *(_QWORD *)(v2 + 128) += v28;
          LODWORD(nn) = sqlite3VdbeFrameRestore(v27, 0x180000000uLL, v8, v17);
          if ( *((_DWORD *)v17 + 2) == 4 )
            LODWORD(nn) = *(_DWORD *)(v6[17] + 24LL * (int)nn + 8) - 1;
          v14 = v6[17];
          v5 = v6[13];
          v9 = v788;
          nn = (int)nn;
          v793 = v14;
          v794 = v5;
          v17 = (unsigned __int8 *)(v14 + 24LL * (int)nn);
          v7 = Table;
          goto LABEL_165;
        }
        v768 = *((_DWORD *)v17 + 1);
        *((_DWORD *)v6 + 13) = v768;
        *((_BYTE *)v6 + 196) = v17[8];
        if ( v768 )
        {
          v769 = *((unsigned __int16 *)v17 + 1);
          if ( (_WORD)v769 )
          {
            sqlite3VdbeError(v6, "%s constraint failed", (const char *)qword_18026F368[v769]);
            v770 = v17;
            if ( *((_QWORD *)v17 + 2) )
              v6[21] = sqlite3MPrintf(v2, "%z: %s", v6[21]);
          }
          else
          {
            sqlite3VdbeError(v6, "%s", *((const char **)v17 + 2));
            v770 = v17;
          }
          sqlite3_log(
            *((unsigned int *)v770 + 1),
            "abort at %d in [%s]: %s",
            (__int64)&v770[-v14] / 24,
            (const char *)v6[31],
            (const char *)v6[21]);
        }
        v11 = v795;
        v285 = sqlite3VdbeHalt(v6);
        v4 = (unsigned __int8 *)v793;
        if ( v285 == 5 )
        {
          *((_DWORD *)v6 + 13) = 5;
        }
        else
        {
          v771 = 101;
          if ( *((_DWORD *)v6 + 13) )
            v771 = 1;
          v285 = v771;
        }
LABEL_1959:
        while ( v19 >= v11 )
        {
          v786 = *(unsigned int (__fastcall **)(_QWORD))(v2 + 512);
          if ( !v786 )
            break;
          v11 += *(unsigned int *)(v2 + 528);
          if ( v786(*(_QWORD *)(v2 + 520)) )
          {
            v11 = -1;
            goto LABEL_1926;
          }
        }
        *((_DWORD *)v6 + 57) += v19;
        return v285;
      case 71:
        v29 = *((int *)v17 + 2);
        v30 = v6[13] + 56 * v29;
        if ( (*(_WORD *)(v30 + 20) & 0x9000) != 0 )
        {
          v31 = out2PrereleaseWithClear(v6[13] + 56 * v29, v30);
          v7 = Table;
          v32 = (_QWORD *)v31;
          v5 = v794;
          v9 = v788;
          v8 = v792;
          nn = *((int *)v17 + 1);
          *v32 = nn;
          v12 = 0x180000000uLL;
          v10 = v805;
          v17 += 24;
        }
        else
        {
          *(_WORD *)(v30 + 20) = 4;
          nn = *((int *)v17 + 1);
          *(_QWORD *)v30 = nn;
LABEL_24:
          v12 = 0x180000000uLL;
          v10 = v805;
          v17 += 24;
        }
        continue;
      case 72:
        v33 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v33 + 20) & 0x9000) != 0 )
        {
          v34 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v33);
          v7 = Table;
          v33 = v34;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          *(_WORD *)(v33 + 20) = 4;
        }
        goto LABEL_28;
      case 73:
        v37 = v17;
        goto LABEL_53;
      case 74:
      case 75:
        v48 = v17;
        v49 = 56LL * *((int *)v17 + 2);
        nn = v49 + v6[13];
        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
        {
          nn = out2PrereleaseWithClear(v49 + v6[13], 36864);
          v48 = v17;
          v5 = v794;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(nn + 20) = 4;
        }
        v50 = (__int16 *)(nn + 20);
        v51 = v48[3] - v48[2];
        v52 = 1;
        if ( v48[1] )
          v52 = 257;
        *v50 = v52;
        *(_DWORD *)(nn + 16) = 0;
        if ( v51 <= 0 )
          goto LABEL_1663;
        do
        {
          v216 = (v50[28] & 0x9000) == 0;
          v50 += 28;
          if ( !v216 )
            nn = vdbeMemClearExternAndSetNull(v50 - 10, 36864, v8);
          --v51;
          *v50 = v52;
          *((_DWORD *)v50 - 1) = 0;
        }
        while ( v51 > 0 );
        goto LABEL_67;
      case 76:
        v53 = 56LL * *((int *)v17 + 1);
        nn = 65473;
        *(_WORD *)(v53 + v5 + 20) &= 0xFFC1u;
        *(_WORD *)(v53 + v5 + 20) |= 1u;
        goto LABEL_71;
      case 77:
        v54 = *((int *)v17 + 2);
        v55 = v6[13] + 56 * v54;
        if ( (*(_WORD *)(v55 + 20) & 0x9000) != 0 )
          v55 = out2PrereleaseWithClear(v6[13] + 56 * v54, 0x180000000uLL);
        else
          *(_WORD *)(v55 + 20) = 4;
        v56 = *((_QWORD *)v17 + 2);
        v57 = *((_DWORD *)v17 + 1);
        if ( v56 )
        {
          nn = sqlite3VdbeMemSetStr(v55, v56, *((int *)v17 + 1), 0, 0);
        }
        else
        {
          if ( (*(_WORD *)(v55 + 20) & 0x9000) != 0 || *(_DWORD *)(v55 + 32) )
            vdbeMemClear(v55);
          *(_WORD *)(v55 + 20) = 1040;
          *(_DWORD *)(v55 + 16) = 0;
          if ( v57 < 0 )
            v57 = 0;
          *(_DWORD *)v55 = v57;
          *(_BYTE *)(v55 + 22) = 1;
          *(_QWORD *)(v55 + 8) = 0;
          nn = sqlite3VdbeMemExpandBlob(v55, v56, v8);
          if ( (_DWORD)nn )
            goto LABEL_82;
        }
        v9 = v788;
        v7 = Table;
        *(_BYTE *)(v55 + 22) = v788;
        goto LABEL_162;
      case 78:
        v58 = v6[16];
        v59 = 56LL * *((int *)v17 + 1);
        v60 = *(_WORD *)(v59 + v58 - 36);
        if ( (v60 & 0x12) != 0 )
        {
          v61 = *(_DWORD *)(v59 + v58 - 40);
          if ( (v60 & 0x400) != 0 )
            v61 += *(_DWORD *)(v59 + v58 - 56);
          if ( v61 > *(_DWORD *)(*(_QWORD *)(v59 + v58 - 32) + 136LL) )
            goto LABEL_1866;
        }
        v62 = (__m128i *)(v5 + 56LL * *((int *)v17 + 2));
        if ( (v62[1].m128i_i16[2] & 0x9000) != 0 )
        {
          vdbeMemClearExternAndSetNull(v62, 0x180000000uLL, v8);
          v7 = Table;
          v12 = 0x180000000uLL;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        _XMM0 = *(__m128i *)(v59 + v58 - 56);
        *v62 = _XMM0;
        v62[1].m128i_i64[0] = *(_QWORD *)(v59 + v58 - 40);
        nn = v62[1].m128i_u16[2];
        LOWORD(nn) = nn & 0x8FBF | 0x2040;
        v62[1].m128i_i16[2] = nn;
        goto LABEL_93;
      case 79:
        v63 = *((_DWORD *)v17 + 3);
        v64 = v5 + 56LL * *((int *)v17 + 1);
        v65 = v5 + 56LL * *((int *)v17 + 2);
        do
        {
          if ( (*(_WORD *)(v65 + 20) & 0x9000) != 0 || *(_DWORD *)(v65 + 32) )
            vdbeMemClear(v65);
          *(_OWORD *)v65 = *(_OWORD *)v64;
          *(_OWORD *)(v65 + 16) = *(_OWORD *)(v64 + 16);
          _XMM0 = *(__m128i *)(v64 + 32);
          *(__m128i *)(v65 + 32) = _XMM0;
          *(_QWORD *)(v65 + 48) = *(_QWORD *)(v64 + 48);
          *(_WORD *)(v64 + 20) = 1;
          *(_DWORD *)(v64 + 32) = 0;
          nn = *(unsigned __int16 *)(v65 + 20);
          if ( (nn & 0x4000) != 0 )
          {
            if ( (nn & 0x12) != 0 )
            {
              if ( (nn & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v65, v12, v8) )
                goto LABEL_82;
              if ( !*(_DWORD *)(v65 + 32) || (nn = *(_QWORD *)(v65 + 40), *(_QWORD *)(v65 + 8) != nn) )
              {
                nn = vdbeMemAddTerminator(v65);
                if ( (_DWORD)nn )
                  goto LABEL_82;
              }
            }
            *(_WORD *)(v65 + 20) &= ~0x4000u;
          }
          v64 += 56LL;
          v65 += 56LL;
          --v63;
        }
        while ( v63 );
        goto LABEL_67;
      case 80:
        v66 = *((_DWORD *)v17 + 3);
        v67 = (__m128i *)(v5 + 56LL * *((int *)v17 + 1));
        v68 = (__m128i *)(v5 + 56LL * *((int *)v17 + 2));
        while ( 2 )
        {
          if ( (v68[1].m128i_i16[2] & 0x9000) != 0 )
          {
            vdbeClrCopy(v68, v67, 0x4000);
          }
          else
          {
            _XMM0 = *v67;
            *v68 = *v67;
            v68[1].m128i_i64[0] = v67[1].m128i_i64[0];
            if ( (v67[1].m128i_i16[2] & 0x2000) == 0 )
            {
              v68[1].m128i_i16[2] &= 0xCFFFu;
              v68[1].m128i_i16[2] |= 0x4000u;
            }
          }
          v69 = v68[1].m128i_i16[2];
          if ( (v69 & 0x4000) == 0 )
            goto LABEL_121;
          if ( (v69 & 0x12) != 0
            && ((v69 & 0x400) != 0 && (unsigned int)sqlite3VdbeMemExpandBlob(v68, v12, v8)
             || (!v68[2].m128i_i32[0] || v68->m128i_i64[1] != v68[2].m128i_i64[1])
             && (unsigned int)vdbeMemAddTerminator(v68)) )
          {
            goto LABEL_82;
          }
          v69 = v68[1].m128i_i16[2] & 0xBFFF;
          v68[1].m128i_i16[2] = v69;
LABEL_121:
          if ( (v69 & 0x800) != 0 && (v17[2] & 2) != 0 )
            v68[1].m128i_i16[2] = v69 & 0xF7FF;
          nn = v66--;
          if ( (_DWORD)nn )
          {
            v68 = (__m128i *)((char *)v68 + 56);
            v67 = (__m128i *)((char *)v67 + 56);
            continue;
          }
          goto LABEL_67;
        }
      case 81:
        v70 = v5 + 56LL * *((int *)v17 + 1);
        nn = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
        {
          v71 = v5 + 56LL * *((int *)v17 + 2);
          goto LABEL_128;
        }
        _XMM0 = *(__m128i *)v70;
        *(_OWORD *)nn = *(_OWORD *)v70;
        *(_QWORD *)(nn + 16) = *(_QWORD *)(v70 + 16);
        v216 = (*(_WORD *)(v70 + 20) & 0x2000) == 0;
        v12 = 0x180000000uLL;
        if ( !v216 )
          goto LABEL_167;
        *(_WORD *)(nn + 20) &= 0xCFFFu;
        *(_WORD *)(nn + 20) |= 0x4000u;
        v10 = v805;
        v17 += 24;
        continue;
      case 82:
        v72 = v5 + 56LL * *((int *)v17 + 2);
        v73 = 56LL * *((int *)v17 + 1);
        nn = *(_QWORD *)(v73 + v5);
        if ( (*(_WORD *)(v72 + 20) & 0x9000) != 0 )
        {
          nn = vdbeReleaseAndSetInt64(v5 + 56LL * *((int *)v17 + 2), *(_QWORD *)(v73 + v5), v72, v7);
          goto LABEL_129;
        }
        *(_QWORD *)v72 = nn;
        *(_WORD *)(v72 + 20) = 4;
        goto LABEL_165;
      case 83:
        if ( v6[10] <= 0 )
        {
          v7 = 0;
          Table = 0;
          v10 = v805;
          v17 += 24;
          continue;
        }
        *((_DWORD *)v6 + 13) = 787;
        *((_BYTE *)v6 + 196) = 2;
        sqlite3VdbeError(v6, "FOREIGN KEY constraint failed", v8, v7);
        LODWORD(v7) = ((*((char *)v6 + 198) >> 7) & 0x312) + 1;
        goto LABEL_288;
      case 84:
        *((_DWORD *)v6 + 11) = (*((_DWORD *)v6 + 11) + 2) | 1;
        v6[20] = v5 + 56LL * *((int *)v17 + 1);
        if ( *(_BYTE *)(v2 + 103) )
          goto LABEL_82;
        if ( (*(_BYTE *)(v2 + 110) & 4) != 0 )
          (*(void (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(v2 + 248))(4, *(_QWORD *)(v2 + 256), v6, 0);
        v285 = 100;
        *((_DWORD *)v6 + 12) = ((int)v17 - (int)v14) / 24 + 1;
        goto LABEL_1906;
      case 85:
        nn = *((int *)v17 + 1);
        if ( !(_DWORD)nn )
          goto LABEL_71;
        nn = v5 + 56 * nn;
        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
        {
          nn = vdbeReleaseAndSetInt64(nn, 0, v8, v7);
          goto LABEL_129;
        }
        *(_QWORD *)nn = 0;
        *(_WORD *)(nn + 20) = 4;
        v10 = v805;
        v17 += 24;
        continue;
      case 86:
        v108 = (_QWORD *)(v5 + 56LL * *((int *)v17 + 1));
        sqlite3VdbeMemIntegerify(v108);
        v7 = Table;
        v5 = v794;
        v9 = v788;
        nn = *((int *)v17 + 2);
        *v108 += nn;
        goto LABEL_165;
      case 87:
        v112 = 56LL * *((int *)v17 + 1);
        nn = *(unsigned __int16 *)(v112 + v5 + 20);
        if ( (nn & 0x24) == 0 )
          goto LABEL_71;
        if ( (nn & 8) != 0 )
          _XMM0.m128i_i64[0] = *(_QWORD *)(v112 + v5);
        else
          *(double *)_XMM0.m128i_i64 = (double)(int)*(_QWORD *)(v112 + v5);
        *(_QWORD *)(v112 + v5) = _XMM0.m128i_i64[0];
        LOWORD(nn) = nn & 0xF240 | 8;
        *(_WORD *)(v112 + v5 + 20) = nn;
        v10 = v805;
        v17 += 24;
        continue;
      case 88:
        v113 = v5 + 56LL * *((int *)v17 + 1);
        if ( (*(_WORD *)(v113 + 20) & 0x400) == 0 )
          goto LABEL_302;
        Table = sqlite3VdbeMemExpandBlob(v5 + 56LL * *((int *)v17 + 1), 0x180000000uLL, v8);
        v7 = Table;
        if ( Table )
        {
          v11 = v795;
          v4 = (unsigned __int8 *)v793;
          goto LABEL_291;
        }
        v9 = v788;
LABEL_302:
        nn = sqlite3VdbeMemCast(v113, v17[8], v9, v7);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 90:
        if ( (v17[2] & 1) != 0 )
          v126 = *((_QWORD *)v17 - 1) + 4LL;
        else
          v126 = 0;
        v127 = *((_QWORD *)v17 + 2);
        v128 = 0;
        v129 = *((_DWORD *)v17 + 1);
        v130 = 0;
        v131 = *((_DWORD *)v17 + 2);
        nn = *((int *)v17 + 3);
        v801 = v127;
        LODWORD(v875) = v129;
        v798 = v131;
        v803 = (unsigned int *)nn;
        if ( nn <= 0 )
        {
          v7 = Table;
          v6 = a1;
          v8 = v792;
          v10 = v805;
          v17 += 24;
        }
        else
        {
          v132 = (_QWORD *)(v127 + 32);
          while ( 1 )
          {
            v133 = v126 ? *(_DWORD *)(v126 + 4 * v130) : v128;
            v134 = v5 + 56LL * (v133 + v131);
            v135 = *(_BYTE *)(*(_QWORD *)(v127 + 24) + v130) & 1;
            v136 = v5 + 56LL * (unsigned int)(v133 + v129);
            nn = sqlite3MemCompare(v136, v134, *v132);
            v792 = nn;
            v8 = (unsigned int)nn;
            if ( (_DWORD)nn )
              break;
            v127 = v801;
            ++v128;
            v129 = v875;
            ++v130;
            v131 = v798;
            ++v132;
            v5 = v794;
            if ( v130 >= (__int64)v803 )
            {
              v7 = Table;
              v12 = 0x180000000uLL;
              v2 = v796;
              v3 = 0;
              v8 = 0;
              v6 = a1;
              v9 = v788;
              v14 = v793;
              v10 = v805;
              v17 = v791 + 24;
              goto LABEL_7;
            }
          }
          nn = *(_QWORD *)(v801 + 24);
          if ( (*(_BYTE *)(v130 + nn) & 2) != 0
            && ((*(_BYTE *)(v136 + 20) & 1) != 0 || (*(_BYTE *)(v134 + 20) & 1) != 0) )
          {
            v8 = (unsigned int)-(int)v8;
            v792 = v8;
          }
          v7 = Table;
          v12 = 0x180000000uLL;
          v2 = v796;
          v216 = v135 == 0;
          v14 = v793;
          v6 = a1;
          v5 = v794;
          v9 = v788;
          if ( !v216 )
          {
            v8 = (unsigned int)-(int)v8;
            v792 = v8;
          }
          v3 = 0;
          v10 = v805;
          v17 = v791 + 24;
        }
        continue;
      case 91:
        v146 = sqlite3VdbeBooleanValue(v5 + 56LL * *((int *)v17 + 1), *((unsigned int *)v17 + 3), v8, v17);
        v5 = v794;
        v149 = v146 ^ (unsigned __int64)*((int *)v17 + 4);
        nn = v794 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
        {
          nn = vdbeReleaseAndSetInt64(v794 + 56LL * *((int *)v17 + 2), v149, v147, v148);
          goto LABEL_129;
        }
        v7 = Table;
        v9 = v788;
        *(_QWORD *)nn = v149;
        *(_WORD *)(nn + 20) = 4;
        goto LABEL_165;
      case 92:
        if ( (*(_BYTE *)(56LL * *((int *)v17 + 1) + v5 + 20) & 1) != 0
          || (*(_BYTE *)(56LL * *((int *)v17 + 3) + v5 + 20) & 1) != 0 )
        {
          nn = v5 + 56LL * *((int *)v17 + 2);
          if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
          {
            nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 2), 0x180000000uLL, v8);
            v7 = Table;
            v5 = v794;
            v9 = v788;
            goto LABEL_165;
          }
          *(_WORD *)(nn + 20) = 1;
          v10 = v805;
          v17 += 24;
        }
        else
        {
          nn = v5 + 56LL * *((int *)v17 + 2);
          if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
          {
            nn = vdbeReleaseAndSetInt64(v5 + 56LL * *((int *)v17 + 2), 0, v8, v7);
            v7 = Table;
            v5 = v794;
            v9 = v788;
            goto LABEL_165;
          }
          *(_QWORD *)nn = 0;
          *(_WORD *)(nn + 20) = 4;
          v10 = v805;
          v17 += 24;
        }
        continue;
      case 94:
        v167 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v168 = *((_DWORD *)v17 + 2);
LABEL_456:
        v798 = v168;
        while ( 1 )
        {
          v169 = *(unsigned int **)(v167 + 88);
          v170 = *((_DWORD *)a1 + 11);
          v803 = v169;
          if ( *(_DWORD *)(v167 + 32) == v170 )
          {
            if ( !**(_BYTE **)(v167 + 48) )
              goto LABEL_482;
          }
          else
          {
            if ( *(_BYTE *)(v167 + 2) )
            {
              if ( *(_BYTE *)v167 == 3 )
              {
                v176 = *(int *)(v167 + 36);
                if ( (int)v176 > 0 )
                {
                  v177 = 56 * v176;
                  v178 = *(_DWORD *)(56 * v176 + v794 + 16);
                  *(_DWORD *)(v167 + 108) = v178;
                  *(_DWORD *)(v167 + 104) = v178;
                  v175 = *(unsigned __int8 **)(v177 + v794 + 8);
                  goto LABEL_476;
                }
              }
              v5 = v794;
              nn = v794 + 56LL * *((int *)v17 + 3);
              if ( (*(_WORD *)(nn + 20) & 0x9000) == 0 )
              {
                v2 = v796;
                v6 = a1;
                v9 = v788;
                *(_WORD *)(nn + 20) = 1;
                goto LABEL_164;
              }
              nn = vdbeMemClearExternAndSetNull(v794 + 56LL * *((int *)v17 + 3), v12, v8);
              v2 = v796;
              v6 = a1;
              goto LABEL_67;
            }
            v171 = *(_QWORD *)(v167 + 48);
            if ( *(_BYTE *)(v167 + 3) )
            {
              v12 = *(_QWORD *)(v167 + 16);
              if ( v12 )
              {
                v172 = *(_DWORD *)(v12 + 4LL * (v168 + 1));
                if ( v172 )
                {
                  v167 = *(_QWORD *)(v167 + 40);
                  v168 = v172 - 1;
                  goto LABEL_456;
                }
              }
              Table = sqlite3VdbeFinishMoveto(v167, v12, v8, v7);
              LODWORD(v7) = Table;
              if ( Table )
                goto LABEL_467;
LABEL_469:
              getCellInfo(v171, v12, v8);
              *(_DWORD *)(v167 + 104) = *(_DWORD *)(v171 + 64);
              v173 = *(unsigned __int16 *)(v171 + 68);
              v174 = *(_DWORD *)(*(_QWORD *)(v171 + 136) + 88LL) - *(_DWORD *)(v171 + 56);
              if ( v173 > v174 )
              {
                v173 = *(_DWORD *)(*(_QWORD *)(v171 + 136) + 88LL) - *(_DWORD *)(v171 + 56);
                if ( v174 < 0 )
                  v173 = 0;
              }
              *(_DWORD *)(v167 + 108) = v173;
              v175 = *(unsigned __int8 **)(v171 + 56);
LABEL_476:
              *(_QWORD *)(v167 + 96) = v175;
              *(_DWORD *)(v167 + 32) = *((_DWORD *)a1 + 11);
              v179 = *v175;
              *v169 = v179;
              if ( v179 >= 0x80 )
                Varint32 = (unsigned __int8)sqlite3GetVarint32(*(_QWORD *)(v167 + 96), v169);
              else
                Varint32 = 1;
              v12 = 64;
              *(_DWORD *)(v167 + 64) = Varint32;
              *(_WORD *)(v167 + 74) = 0;
              if ( *(_DWORD *)(v167 + 108) >= *v169 )
              {
                v181 = *(_QWORD *)(v167 + 96);
LABEL_496:
                v801 = v181;
                goto LABEL_497;
              }
              *(_QWORD *)(v167 + 96) = 0;
              *(_DWORD *)(v167 + 108) = 0;
              if ( *v169 <= 0x18003 && *v169 <= *(_DWORD *)(v167 + 104) )
              {
LABEL_482:
                if ( *(unsigned __int16 *)(v167 + 74) > v168 )
                {
                  LODWORD(v191) = *(_DWORD *)(v167 + 4LL * v168 + 120);
                  goto LABEL_536;
                }
                if ( *(_DWORD *)(v167 + 64) >= *v169 )
                {
                  LODWORD(v191) = 0;
                  goto LABEL_515;
                }
                v181 = *(_QWORD *)(v167 + 96);
                v801 = v181;
                if ( !v181 )
                {
                  v822 = 0;
                  _XMM0.m128i_i64[0] = 0;
                  v819 = 0;
                  v820 = 0;
                  v821 = 0;
                  v182 = *(_QWORD *)(v167 + 48);
                  v8 = *v169;
                  v183 = *(unsigned __int16 *)(v182 + 68);
                  v184 = *(_DWORD *)(*(_QWORD *)(v182 + 136) + 88LL) - *(_DWORD *)(v182 + 56);
                  if ( v183 > v184 )
                  {
                    v183 = *(_DWORD *)(*(_QWORD *)(v182 + 136) + 88LL) - *(_DWORD *)(v182 + 56);
                    if ( v184 < 0 )
                      v183 = 0;
                  }
                  v181 = *(_QWORD *)(v182 + 56);
                  v801 = v181;
                  *((_QWORD *)&v819 + 1) = v181;
                  if ( (unsigned int)v8 <= v183 )
                  {
                    LODWORD(v820) = v8;
                    WORD2(v820) = 16400;
                    Table = 0;
                    goto LABEL_497;
                  }
                  _mm_lfence();
                  Table = sqlite3VdbeMemFromBtree(v182, 0, v8, &v819);
                  v7 = Table;
                  if ( !Table )
                  {
                    v181 = *((_QWORD *)&v819 + 1);
                    goto LABEL_496;
                  }
LABEL_467:
                  v2 = v796;
                  v6 = a1;
                  goto LABEL_289;
                }
LABEL_497:
                v185 = *(unsigned __int16 *)(v167 + 74);
                v186 = v185;
                v187 = v803;
                v188 = (unsigned __int8 *)(v181 + *(unsigned int *)(v167 + 64));
                v189 = v169[v185];
                v190 = v181 + *v169;
                while ( 1 )
                {
                  v191 = *v188;
                  LODWORD(v875) = v191;
                  *(_DWORD *)(v167 + 4 * v186 + 120) = v191;
                  if ( (unsigned int)v191 >= 0x80 )
                  {
                    v193 = sqlite3GetVarint32(v188, &v875);
                    v191 = (unsigned int)v875;
                    v188 += v193;
                    *(_DWORD *)(v167 + 4 * v186 + 120) = v875;
                    v192 = (unsigned int)v191 < 0x80
                         ? *((unsigned __int8 *)qword_18026F230 + v191)
                         : (unsigned int)(v191 - 12) >> 1;
                    v187 = v803;
                  }
                  else
                  {
                    v12 = 0x180000000uLL;
                    ++v188;
                    v192 = *((unsigned __int8 *)qword_18026F230 + v191);
                  }
                  LODWORD(v185) = v185 + 1;
                  v189 += v192;
                  v186 = (int)v185;
                  v187[(int)v185] = v189;
                  if ( (unsigned int)v185 > v798 )
                    break;
                  if ( (unsigned __int64)v188 >= v190 )
                    goto LABEL_508;
                }
                if ( (unsigned __int64)v188 < v190 )
                {
                  if ( v189 <= *(unsigned int *)(v167 + 104) )
                    goto LABEL_510;
                }
                else
                {
LABEL_508:
                  if ( (unsigned __int64)v188 <= v190 && v189 == *(_DWORD *)(v167 + 104) )
                  {
LABEL_510:
                    v194 = (_DWORD)v188 - v801;
                    *(_WORD *)(v167 + 74) = v185;
                    *(_DWORD *)(v167 + 64) = v194;
                    if ( !*(_QWORD *)(v167 + 96) && ((WORD2(v820) & 0x9000) != 0 || (_DWORD)v821) )
                      vdbeMemClear(&v819);
                    v169 = v803;
                    v3 = 0;
                    v168 = v798;
LABEL_515:
                    if ( *(unsigned __int16 *)(v167 + 74) <= v168 )
                    {
                      v5 = v794;
                      nn = v794 + 56LL * *((int *)v791 + 3);
                      if ( v791[1] == 0xF6 )
                      {
                        v195 = (__m128i *)*((_QWORD *)v791 + 2);
                        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
                        {
                          nn = vdbeClrCopy(v794 + 56LL * *((int *)v791 + 3), *((_QWORD *)v791 + 2), 0x2000);
                          v2 = v796;
                          v6 = a1;
                          goto LABEL_67;
                        }
                        _XMM0 = *v195;
                        v7 = Table;
                        v2 = v796;
                        v17 = v791;
                        v6 = a1;
                        *(__m128i *)nn = *v195;
                        *(_QWORD *)(nn + 16) = v195[1].m128i_i64[0];
                        if ( (v195[1].m128i_i16[2] & 0x2000) == 0 )
                        {
                          v9 = v788;
                          *(_WORD *)(nn + 20) &= 0xAFFFu;
                          *(_WORD *)(nn + 20) |= 0x2000u;
                          goto LABEL_164;
                        }
LABEL_1124:
                        v9 = v788;
                        v3 = 0;
                        goto LABEL_164;
                      }
                      if ( (*(_WORD *)(nn + 20) & 0x9000) == 0 )
                      {
                        v7 = Table;
                        v2 = v796;
                        v17 = v791;
                        v6 = a1;
                        v9 = v788;
                        *(_WORD *)(nn + 20) = 1;
                        goto LABEL_164;
                      }
                      nn = vdbeMemClearExternAndSetNull(v794 + 56LL * *((int *)v791 + 3), v12, v8);
                      v2 = v796;
                      v6 = a1;
LABEL_67:
                      v7 = Table;
                      goto LABEL_68;
                    }
LABEL_536:
                    v197 = v791;
                    v198 = v794 + 56LL * *((int *)v791 + 3);
                    if ( (*(_WORD *)(v198 + 20) & 0x9000) != 0 )
                    {
                      vdbeMemClearExternAndSetNull(v794 + 56LL * *((int *)v791 + 3), v791, v8);
                      v197 = v791;
                    }
                    if ( *(_DWORD *)(v167 + 108) < v169[v168 + 1] )
                    {
                      *(_BYTE *)(v198 + 22) = v788;
                      v203 = v197[2] & 0xC0;
                      if ( v203 && (v203 == (char)0x80 || (unsigned int)v191 >= 0xC && ((v191 & 1) == 0 || v203 == -64))
                        || ((unsigned int)v191 < 0x80
                          ? (v204 = *((unsigned __int8 *)qword_18026F230 + (unsigned int)v191))
                          : (v204 = (unsigned int)(v191 - 12) >> 1),
                            !v204) )
                      {
                        nn = sqlite3VdbeSerialGet(&qword_18026E9A0, (unsigned int)v191, v198, v7);
                        v2 = v796;
                        v6 = a1;
                        goto LABEL_67;
                      }
                      v205 = v169[v168];
                      v6 = a1;
                      nn = vdbeColumnFromOverflow(v167, v168, v191, v205, *((_DWORD *)a1 + 11), v802, v198);
                      v2 = v796;
                      v7 = (unsigned int)nn;
                      Table = nn;
                      if ( !(_DWORD)nn )
                        goto LABEL_68;
                      if ( (_DWORD)nn == 7 )
                        goto LABEL_82;
                      if ( (_DWORD)nn != 18 )
                        goto LABEL_289;
                    }
                    else
                    {
                      v199 = (const void *)(*(_QWORD *)(v167 + 96) + v169[v168]);
                      if ( (unsigned int)v191 < 0xC )
                      {
                        nn = sqlite3VdbeSerialGet(v199, (unsigned int)v191, v198, v7);
                        v2 = v796;
                        v6 = a1;
                        goto LABEL_67;
                      }
                      v200 = (unsigned int)(v191 - 12) >> 1;
                      *(_DWORD *)(v198 + 16) = v200;
                      *(_BYTE *)(v198 + 22) = v788;
                      v201 = (unsigned int)(v200 + 2);
                      if ( *(_DWORD *)(v198 + 32) >= (int)v201 )
                      {
                        *(_QWORD *)(v198 + 8) = *(_QWORD *)(v198 + 40);
                        goto LABEL_547;
                      }
                      if ( (int)v200 <= *(_DWORD *)(v796 + 136) )
                      {
                        _mm_lfence();
                        *(_WORD *)(v198 + 20) = 1;
                        if ( (unsigned int)sqlite3VdbeMemGrow(v198, v201, 0, v7) )
                          goto LABEL_544;
LABEL_547:
                        memmove(*(void **)(v198 + 8), v199, (unsigned int)(v191 - 12) >> 1);
                        v12 = 0x180000000uLL;
                        v7 = Table;
                        v2 = v796;
                        v6 = a1;
                        v5 = v794;
                        v9 = v788;
                        v8 = v792;
                        *(_BYTE *)(v200 + *(_QWORD *)(v198 + 8)) = 0;
                        *(_BYTE *)(*(_QWORD *)(v198 + 8) + v200 + 1) = 0;
                        v202 = v191;
                        v14 = v793;
                        nn = (unsigned __int16)word_18026F3BC[v202 & 1];
                        *(_WORD *)(v198 + 20) = nn;
                        v10 = v805;
                        v17 = v791 + 24;
                        goto LABEL_7;
                      }
                      v2 = v796;
LABEL_1865:
                      v6 = a1;
                    }
LABEL_1866:
                    sqlite3VdbeError(v6, "string or blob too big");
                    LODWORD(v7) = 18;
                    goto LABEL_288;
                  }
                }
                if ( !*v187 )
                {
                  v8 = 0;
                  LODWORD(v188) = v190;
                  LOWORD(v185) = 0;
                  goto LABEL_510;
                }
                if ( !*(_QWORD *)(v167 + 96) && ((WORD2(v820) & 0x9000) != 0 || (_DWORD)v821) )
                  vdbeMemClear(&v819);
                v3 = 0;
              }
              v14 = v793;
              v196 = *(_DWORD *)(v793 + 12);
              if ( v196 <= 0 )
              {
                LODWORD(v7) = sqlite3CorruptError(96586);
                Table = v7;
                goto LABEL_1840;
              }
              v2 = v796;
              v6 = a1;
              nn = 3LL * (v196 - 1);
              v791 = (unsigned __int8 *)(v793 + 8 * nn);
LABEL_129:
              v7 = Table;
LABEL_130:
              v17 = v791;
              v5 = v794;
              v9 = v788;
              goto LABEL_165;
            }
            if ( !*(_BYTE *)v171 )
              goto LABEL_469;
          }
          Table = sqlite3VdbeHandleMovedCursor(v167, v12, v8, v7);
          v7 = Table;
          if ( Table )
            goto LABEL_467;
        }
      case 95:
        v206 = 0;
        v207 = *((_QWORD *)v17 + 2);
        nn = *((int *)v17 + 1);
        v208 = *(_QWORD *)(v207 + 8);
        v209 = v5 + 56 * nn;
        if ( *(__int16 *)(v207 + 54) <= 0 )
        {
          v2 = v796;
          v10 = v805;
          v17 = v791 + 24;
          continue;
        }
        v210 = v208 + 12;
        while ( 1 )
        {
          v211 = *(_WORD *)(v210 + 6);
          if ( (v211 & 0x60) == 0 )
            goto LABEL_567;
          if ( (v211 & 0x20) == 0 )
            break;
LABEL_597:
          nn = (unsigned int)*(__int16 *)(v207 + 54);
          ++v206;
          v210 += 24;
          if ( v206 >= (int)nn )
          {
            v7 = Table;
            v2 = v796;
            goto LABEL_162;
          }
        }
        if ( *((_DWORD *)v791 + 3) )
          goto LABEL_596;
LABEL_567:
        v212 = *(_BYTE *)v210;
        if ( *(char *)v210 < 67 )
        {
          if ( v212 == 66 )
          {
            v214 = *(_WORD *)(v209 + 20);
            if ( (v214 & 2) == 0 && (v214 & 0x2C) != 0 )
            {
              LOBYTE(v8) = 1;
              sqlite3VdbeMemStringify(v209, v9, v8, v7);
            }
            *(_WORD *)(v209 + 20) &= 0xFFD3u;
          }
        }
        else
        {
          v213 = *(_WORD *)(v209 + 20);
          if ( (v213 & 4) == 0 )
          {
            if ( (v213 & 0x28) != 0 )
            {
              if ( v212 <= 69 )
                sqlite3VdbeIntegerAffinity(v209, v12, v8, v7);
            }
            else if ( (v213 & 2) != 0 )
            {
              applyNumericAffinity(v209, 1, v8, v7);
            }
          }
        }
        v215 = *(_WORD *)(v209 + 20);
        v12 = v215;
        if ( (v215 & 1) != 0 )
          goto LABEL_595;
        switch ( (*(_DWORD *)(v210 - 4) >> 4) & 0xF )
        {
          case 2:
            v216 = (v215 & 0x10) == 0;
            break;
          case 3:
          case 4:
            v216 = (v215 & 4) == 0;
            break;
          case 5:
            if ( (v215 & 4) != 0 )
            {
              v217 = *(double *)v209;
              v7 = 0xFFFFFFFFFFFFLL;
              if ( (unsigned __int64)(*(_QWORD *)v209 + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
              {
                v218 = v215 | 8;
                *(double *)_XMM0.m128i_i64 = (double)SLODWORD(v217);
                *(double *)v209 = (double)SLODWORD(v217);
              }
              else
              {
                v218 = v215 | 0x20;
              }
              *(_WORD *)(v209 + 20) = v218;
              v12 = v209 + 20;
              *(_WORD *)(v209 + 20) = v218 & 0xFFFB;
              goto LABEL_595;
            }
            v216 = (v215 & 0x28) == 0;
            break;
          case 6:
            v216 = (v215 & 2) == 0;
            break;
          default:
LABEL_595:
            v9 = v788;
LABEL_596:
            v209 += 56LL;
            goto LABEL_597;
        }
        if ( v216 )
        {
          sqlite3VdbeError(
            v6,
            "cannot store %s value in %s column %s.%s",
            (const char *)qword_1803384B0[*((unsigned __int8 *)qword_18026F2C0 + (v215 & 0x3F))],
            off_180337B90[((*(_DWORD *)(v208 + 24LL * v206 + 8) >> 4) & 0xFu) - 1],
            *(const char **)v207,
            *(const char **)(v208 + 24LL * v206));
          v2 = v796;
          LODWORD(v7) = 3091;
          Table = 3091;
          goto LABEL_289;
        }
        goto LABEL_595;
      case 96:
        v219 = (_BYTE *)*((_QWORD *)v17 + 2);
        LOBYTE(nn) = *v219;
        for ( n = v5 + 56LL * *((int *)v17 + 1); ; n += 56LL )
        {
          if ( (char)nn < 67 )
          {
            if ( (_BYTE)nn == 66 )
            {
              v222 = *(_WORD *)(n + 20);
              if ( (v222 & 2) == 0 && (v222 & 0x2C) != 0 )
              {
                LOBYTE(v8) = 1;
                sqlite3VdbeMemStringify(n, v9, v8, v7);
              }
              *(_WORD *)(n + 20) &= 0xFFD3u;
            }
          }
          else
          {
            v221 = *(_WORD *)(n + 20);
            if ( (v221 & 4) == 0 )
            {
              if ( (v221 & 0x28) != 0 )
              {
                if ( (char)nn <= 69 )
                  sqlite3VdbeIntegerAffinity(n, v12, v8, v7);
              }
              else if ( (v221 & 2) != 0 )
              {
                applyNumericAffinity(n, 1, v8, v7);
              }
            }
          }
          if ( *v219 == 69 )
          {
            v223 = *(_WORD *)(n + 20);
            if ( (v223 & 4) != 0 )
            {
              v12 = *(_QWORD *)n;
              v8 = 0xFFFFFFFFFFFFLL;
              if ( (unsigned __int64)(*(_QWORD *)n + 0x800000000000LL) > 0xFFFFFFFFFFFFLL )
              {
                *(double *)_XMM0.m128i_i64 = (double)(int)v12;
                v224 = v223 & 0xFFF1 | 8;
                *(double *)n = (double)(int)v12;
              }
              else
              {
                v224 = v223 & 0xFFDB | 0x20;
              }
              *(_WORD *)(n + 20) = v224;
            }
          }
          nn = (unsigned __int8)*++v219;
          if ( !(_BYTE)nn )
            break;
          v9 = v788;
        }
        v7 = Table;
        v3 = 0;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 97:
        v225 = 0;
        v226 = v794;
        v227 = 0;
        v228 = 0;
        v229 = (_BYTE *)*((_QWORD *)v17 + 2);
        v230 = v794 + 56LL * *((int *)v17 + 1);
        v231 = 56LL * *((int *)v17 + 3);
        v232 = (unsigned int *)(v230 + 56LL * (*((_DWORD *)v17 + 2) - 1));
        v801 = v230;
        v803 = v232;
        v875 = v231 + v794;
        if ( v229 )
        {
          v233 = (_WORD *)(v230 + 20);
          do
          {
            applyAffinity(v233 - 10, (unsigned __int8)*v229, v9, v7);
            if ( *v229 == 69 && (*v233 & 4) != 0 )
              *v233 = *v233 & 0xFFDB | 0x20;
            v9 = v788;
            ++v229;
            v233 += 28;
          }
          while ( *v229 );
          v230 = v801;
          v232 = v803;
        }
        v234 = v232 + 9;
        while ( 2 )
        {
          v235 = *((_WORD *)v234 - 8);
          if ( (v235 & 1) != 0 )
          {
            LODWORD(v3) = v3 + 1;
            v225 = 1;
            v236 = (v235 & 0x400) != 0 ? 0xA : 0;
          }
          else if ( (v235 & 0x24) != 0 )
          {
            v237 = *(_QWORD *)(v234 - 9);
            v226 = v237;
            if ( v237 < 0 )
              v226 = ~v237;
            LODWORD(v3) = v3 + 1;
            if ( v226 > 0x7F )
            {
              if ( v226 > 0x7FFF )
              {
                if ( v226 > 0x7FFFFF )
                {
                  if ( v226 > 0x7FFFFFFF )
                  {
                    if ( v226 > 0x7FFFFFFFFFFFLL )
                    {
                      v227 += 8;
                      if ( (v235 & 0x20) != 0 )
                      {
                        *(double *)_XMM0.m128i_i64 = (double)(int)v237;
                        v236 = 7;
                        v225 = 1;
                        *(_QWORD *)(v234 - 9) = _XMM0.m128i_i64[0];
                        *((_WORD *)v234 - 8) = v235 & 0xFFD7 | 8;
                      }
                      else
                      {
                        v236 = 6;
                        v225 = 1;
                      }
                    }
                    else
                    {
                      v227 += 6;
                      v236 = 5;
                      v225 = 1;
                    }
                  }
                  else
                  {
                    v227 += 4;
                    v236 = 4;
                    v225 = 1;
                  }
                }
                else
                {
                  v227 += 3;
                  v236 = 3;
                  v225 = 1;
                }
              }
              else
              {
                v227 += 2;
                v236 = 2;
                v225 = 1;
              }
            }
            else if ( (*(_QWORD *)(v234 - 9) & 1LL) == v237 && *((_BYTE *)a1 + 197) >= 4u )
            {
              v236 = v226 + 8;
              v225 = 1;
            }
            else
            {
              v236 = 1;
              ++v227;
              v225 = 1;
            }
          }
          else if ( (v235 & 8) != 0 )
          {
            LODWORD(v3) = v3 + 1;
            v236 = 7;
            v227 += 8;
            v225 = 1;
          }
          else
          {
            v238 = *(v234 - 5);
            v236 = ((v235 >> 1) & 1) + 2 * (v238 + 6);
            if ( (v235 & 0x400) != 0 )
            {
              v239 = (int)*(v234 - 9);
              v236 += 2 * v239;
              if ( v227 )
              {
                if ( (unsigned int)sqlite3VdbeMemExpandBlob(v234 - 9, v226, v225) )
                {
LABEL_544:
                  v2 = v796;
                  goto LABEL_545;
                }
                v238 += *(v234 - 9);
              }
              else
              {
                v228 += v239;
              }
            }
            v225 = 1;
            v227 += v238;
            v240 = 1;
            for ( ii = (unsigned __int64)v236 >> 7; ii; ii >>= 7 )
              ++v240;
            v230 = v801;
            LODWORD(v3) = v240 + v3;
          }
          *v234 = v236;
          if ( v234 - 9 != (unsigned int *)v230 )
          {
            v234 -= 14;
            continue;
          }
          break;
        }
        if ( (int)v3 <= 126 )
          goto LABEL_667;
        v242 = 1;
        for ( jj = (unsigned __int64)(int)v3 >> 7; jj; jj >>= 7 )
          ++v242;
        LODWORD(v3) = v242 + v3;
        v244 = 1;
        for ( kk = (unsigned __int64)(int)v3 >> 7; kk; kk >>= 7 )
          ++v244;
        if ( v242 < v244 )
LABEL_667:
          LODWORD(v3) = v3 + 1;
        v246 = v875;
        v247 = v227 + (int)v3;
        v248 = *(int *)(v875 + 32);
        if ( v247 + v228 <= v248 )
          goto LABEL_673;
        v2 = v796;
        if ( v247 + v228 > *(int *)(v796 + 136) )
          goto LABEL_1865;
        if ( (int)v248 >= (int)v247 )
        {
LABEL_673:
          *(_QWORD *)(v875 + 8) = *(_QWORD *)(v875 + 40);
          goto LABEL_674;
        }
        _mm_lfence();
        if ( !(unsigned int)sqlite3VdbeMemGrow(v875, (unsigned int)v247, 0, v7) )
        {
          v230 = v801;
LABEL_674:
          *(_DWORD *)(v246 + 16) = v247;
          *(_WORD *)(v246 + 20) = 16;
          if ( v228 )
          {
            *(_DWORD *)v246 = v228;
            *(_WORD *)(v246 + 20) = 1040;
          }
          v249 = *(_BYTE **)(v246 + 8);
          v250 = &v249[(int)v3];
          if ( (int)v3 >= 128 )
          {
            if ( (unsigned int)v3 > 0x3FFF )
            {
              v252 = putVarint64(*(_QWORD *)(v246 + 8), (int)v3);
            }
            else
            {
              v252 = 2;
              *v249 = ((unsigned __int64)(int)v3 >> 7) | 0x80;
              v249[1] = v3 & 0x7F;
            }
            v251 = &v249[v252];
          }
          else
          {
            *v249 = v3;
            v251 = v249 + 1;
          }
          v253 = (int *)v803;
          for ( mm = (int *)(v230 + 16); ; mm += 14 )
          {
            v255 = (unsigned int)mm[5];
            if ( (unsigned int)v255 > 7 )
            {
              if ( (unsigned int)v255 >= 0x80 )
              {
                if ( (unsigned int)v255 > 0x3FFF )
                {
                  v261 = putVarint64(v251, v255);
                }
                else
                {
                  *v251 = ((unsigned int)v255 >> 7) | 0x80;
                  v251[1] = v255 & 0x7F;
                  v261 = 2;
                }
                v251 += v261;
                v260 = *mm;
                if ( (_DWORD)v260 )
                {
LABEL_704:
                  memmove(v250, *((const void **)mm - 1), v260);
                  v250 += *mm;
                }
              }
              else
              {
                *v251++ = v255;
                if ( (unsigned int)v255 >= 0xE )
                {
                  v260 = *mm;
                  if ( (int)v260 > 0 )
                    goto LABEL_704;
                }
              }
            }
            else
            {
              *v251++ = v255;
              if ( (_DWORD)v255 )
              {
                v256 = *((_QWORD *)mm - 2);
                v257 = *((unsigned __int8 *)qword_18026F230 + (unsigned int)v255);
                if ( (_DWORD)v257 != 1 )
                {
                  if ( (_DWORD)v257 != 2 )
                  {
                    if ( (_DWORD)v257 != 3 )
                    {
                      if ( (_DWORD)v257 != 4 )
                      {
                        if ( (_DWORD)v257 != 6 )
                        {
                          v250[7] = v256;
                          v258 = v256 >> 8;
                          v250[6] = v258;
                          v256 = v258 >> 8;
                        }
                        v250[5] = v256;
                        v259 = v256 >> 8;
                        v250[4] = v259;
                        v256 = v259 >> 8;
                      }
                      v250[3] = v256;
                      v256 >>= 8;
                    }
                    v250[2] = v256;
                    v256 >>= 8;
                  }
                  v250[1] = v256;
                  v256 >>= 8;
                }
                *v250 = v256;
                v250 += v257;
              }
            }
            nn = (__int64)(mm - 4);
            if ( mm - 4 == v253 )
            {
              v7 = Table;
              v2 = v796;
              v6 = a1;
              goto LABEL_1122;
            }
          }
        }
LABEL_545:
        v6 = a1;
        goto LABEL_82;
      case 98:
        v262 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v263 = *(_QWORD *)(v262 + 48);
        if ( *((_DWORD *)v17 + 3) )
        {
          v265 = sqlite3BtreeRowCountEst(*(_QWORD *)(v262 + 48));
        }
        else
        {
          v801 = 0;
          Table = sqlite3BtreeCount(v2, v263, &v801);
          LODWORD(v7) = Table;
          if ( Table )
            goto LABEL_289;
          v265 = v801;
        }
        v266 = 56LL * *((int *)v17 + 2) + v6[13];
        if ( (*(_WORD *)(v266 + 20) & 0x9000) != 0 )
        {
          *(_QWORD *)out2PrereleaseWithClear(56LL * *((int *)v17 + 2) + v6[13], v264) = v265;
        }
        else
        {
          *(_WORD *)(v266 + 20) = 4;
          *(_QWORD *)v266 = v265;
        }
        goto LABEL_1361;
      case 99:
        v298 = *((_DWORD *)v17 + 3);
        v299 = *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 8);
        v300 = *(_QWORD **)(v299 + 8);
        if ( v298 == 15 )
          v301 = *(_DWORD *)(*v300 + 132LL) + *(_DWORD *)(v299 + 28);
        else
          v301 = _byteswap_ulong(*(_DWORD *)(4 * v298 + 36 + *(_QWORD *)(v300[3] + 80LL)));
        v302 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v302 + 20) & 0x9000) != 0 )
        {
          v303 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v302);
          v7 = Table;
          v302 = v303;
          v5 = v794;
          v9 = v788;
          v8 = v792;
          nn = v301;
        }
        else
        {
          nn = v301;
          *(_WORD *)(v302 + 20) = 4;
        }
        *(_QWORD *)v302 = v301;
        goto LABEL_30;
      case 100:
        v304 = *(_QWORD *)(v2 + 32);
        v305 = 32LL * *((int *)v17 + 1);
        updated = sqlite3BtreeUpdateMeta(
                    *(_QWORD *)(v305 + v304 + 8),
                    *((unsigned int *)v17 + 2),
                    *((unsigned int *)v17 + 3),
                    v7);
        v7 = updated;
        Table = updated;
        nn = *((unsigned int *)v17 + 2);
        if ( (_DWORD)nn == 1 )
        {
          **(_DWORD **)(v305 + v304 + 24) = *((_DWORD *)v17 + 3) - *((unsigned __int16 *)v17 + 1);
          *(_DWORD *)(v2 + 44) |= 1u;
          nn = sqlite3FkClearTriggerCache(v2, *((unsigned int *)v17 + 1));
          v7 = Table;
        }
        else if ( (_DWORD)nn == 2 )
        {
          nn = v17[12];
          *(_BYTE *)(*(_QWORD *)(v305 + v304 + 24) + 112LL) = nn;
        }
        if ( *((_DWORD *)v17 + 1) == 1 )
        {
          for ( nn = *(_QWORD *)(v2 + 8); nn; nn = *(_QWORD *)(nn + 16) )
          {
            *(_DWORD *)(nn + 200) &= ~2u;
            *(_DWORD *)(nn + 200) |= 1u;
          }
          *((_DWORD *)v6 + 50) &= 0xFFFFFFFC;
        }
        if ( (_DWORD)v7 )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 101:
        v307 = v17;
        v308 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        if ( !v308 || *(_DWORD *)(v308 + 68) != *((_DWORD *)v17 + 2) )
          goto LABEL_831;
        sqlite3BtreeClearCursor(*(_QWORD *)(v308 + 48), 0x180000000uLL, v8);
        v7 = Table;
        goto LABEL_844;
      case 102:
      case 103:
      case 104:
      case 105:
        v98 = v5 + 56LL * *((int *)v17 + 1);
        v99 = v5 + 56LL * *((int *)v17 + 2);
        v100 = v5 + 56LL * *((int *)v17 + 3);
        if ( ((*(_BYTE *)(v99 + 20) | *(_BYTE *)(v98 + 20)) & 1) != 0 )
        {
          nn = 36864;
          if ( (*(_WORD *)(v100 + 20) & 0x9000) != 0 )
          {
            nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 3), 0x180000000uLL, v8);
            v7 = Table;
            v5 = v794;
            v9 = v788;
            goto LABEL_164;
          }
          *(_WORD *)(v100 + 20) = 1;
          v14 = v793;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v101 = sqlite3_value_int64(v99, 0x180000000uLL, v8);
        v104 = sqlite3_value_int64(v98, v102, v103);
        v105 = v104;
        v106 = *v17;
        if ( *v17 == 102 )
        {
          v101 &= v104;
LABEL_277:
          v7 = Table;
          nn = 62020;
          v5 = v794;
          v9 = v788;
          *(_QWORD *)v100 = v101;
          *(_WORD *)(v100 + 20) &= 0xF244u;
          *(_WORD *)(v100 + 20) |= 4u;
          goto LABEL_164;
        }
        if ( v106 == 103 )
        {
          v101 |= v104;
          goto LABEL_277;
        }
        if ( !v104 )
          goto LABEL_277;
        if ( v104 >= 0 )
          goto LABEL_267;
        v106 = -47 - v106;
        if ( v104 > -64 )
        {
          v105 = -v104;
LABEL_267:
          if ( v105 < 64 )
          {
            if ( v106 == 104 )
            {
              v107 = v101 << v105;
            }
            else
            {
              v107 = (unsigned __int64)v101 >> v105;
              if ( v101 < 0 )
                v107 |= -1LL << (64 - (unsigned __int8)v105);
            }
            v101 = v107;
            goto LABEL_277;
          }
        }
        if ( v101 >= 0 || v106 == 104 )
          v101 = 0;
        else
          v101 = -1;
        goto LABEL_277;
      case 106:
      case 107:
      case 108:
      case 109:
      case 110:
        v83 = v5 + 56LL * *((int *)v17 + 1);
        v84 = *(_WORD *)(v83 + 20);
        v85 = v5 + 56LL * *((int *)v17 + 2);
        v86 = v5 + 56LL * *((int *)v17 + 3);
        v87 = *(_WORD *)(v85 + 20);
        if ( ((unsigned __int8)v84 & (unsigned __int8)v87 & 4) != 0 )
          goto LABEL_175;
        if ( (((unsigned __int8)v87 | (unsigned __int8)v84) & 1) != 0 )
          goto LABEL_246;
        v88 = *(_WORD *)(v83 + 20) & 0x2D;
        if ( !v88 )
          LOBYTE(v88) = computeNumericType(v5 + 56LL * *((int *)v17 + 1), 0x180000000uLL, v8, v7);
        v89 = *(_WORD *)(v85 + 20) & 0x2D;
        if ( !v89 )
          LOBYTE(v89) = computeNumericType(v85, v12, v8, v7);
        if ( ((unsigned __int8)v88 & (unsigned __int8)v89 & 4) == 0 )
          goto LABEL_217;
LABEL_175:
        v7 = *(_QWORD *)v83;
        v8 = *(_QWORD *)v85;
        if ( *v17 == 106 )
        {
          if ( v7 < 0 )
          {
            if ( v8 < 0 && (__int64)(0x8000000000000001uLL - v8) > v7 + 1 )
              goto LABEL_217;
          }
          else if ( v8 > 0 && 0x7FFFFFFFFFFFFFFFLL - v8 < v7 )
          {
            goto LABEL_217;
          }
        }
        else
        {
          if ( *v17 != 107 )
          {
            if ( *v17 == 108 )
            {
              if ( v7 <= 0 )
              {
                if ( v7 < 0 )
                {
                  if ( v8 > 0 )
                  {
                    v12 = (__int64)0x8000000000000000uLL % v8;
                    if ( v7 >= (__int64)0x8000000000000000uLL / v8 )
                    {
                      v90 = v7 * v8;
                      goto LABEL_207;
                    }
                    goto LABEL_217;
                  }
                  if ( v8 < 0 )
                  {
                    if ( v7 == 0x8000000000000000uLL )
                      goto LABEL_217;
                    if ( v8 == 0x8000000000000000uLL )
                      goto LABEL_217;
                    v12 = (__int64)0x8000000000000001uLL % v7;
                    if ( -v8 > (__int64)0x8000000000000001uLL / v7 )
                      goto LABEL_217;
                  }
                }
                v90 = v7 * v8;
                goto LABEL_207;
              }
              v12 = 0x7FFFFFFFFFFFFFFFLL % v7;
              if ( v8 <= 0x7FFFFFFFFFFFFFFFLL / v7 )
              {
                v12 = (__int64)0x8000000000000000uLL % v7;
                if ( v8 >= (__int64)0x8000000000000000uLL / v7 )
                {
                  v90 = v7 * v8;
                  goto LABEL_207;
                }
              }
            }
            else
            {
              if ( *v17 != 109 )
              {
                if ( v7 )
                {
                  if ( v7 == -1 )
                    v7 = 1;
                  v90 = v8 % v7;
                  goto LABEL_207;
                }
LABEL_245:
                v7 = Table;
                v8 = v792;
LABEL_246:
                nn = 36864;
                if ( (*(_WORD *)(v86 + 20) & 0x9000) == 0 )
                {
                  v12 = 0x180000000uLL;
                  v5 = v794;
                  v9 = v788;
                  v14 = v793;
                  *(_WORD *)(v86 + 20) = 1;
                  v2 = v796;
                  v10 = v805;
                  v17 += 24;
                  continue;
                }
                nn = vdbeMemClearExternAndSetNull(v86, v12, v8);
                v7 = Table;
LABEL_248:
                v2 = v796;
                v17 = v791;
                v5 = v794;
                v9 = v788;
                goto LABEL_164;
              }
              if ( !v7 )
                goto LABEL_245;
              if ( v7 != -1 || v8 != 0x8000000000000000uLL )
              {
                v90 = v8 / v7;
LABEL_207:
                *(_QWORD *)v86 = v90;
                nn = *(unsigned __int16 *)(v86 + 20);
                LOWORD(nn) = nn & 0xF240 | 4;
                *(_WORD *)(v86 + 20) = nn;
                v2 = v796;
                goto LABEL_67;
              }
            }
LABEL_217:
            v91 = *(_WORD *)(v83 + 20);
            if ( (v91 & 8) != 0 )
            {
              v92 = *(double *)v83;
            }
            else if ( (v91 & 0x24) != 0 )
            {
              v92 = (double)(int)*(_QWORD *)v83;
            }
            else if ( (v91 & 0x12) != 0 )
            {
              v92 = memRealValue(v83, v12, v8, v7);
            }
            else
            {
              v92 = 0.0;
            }
            v93 = *(_WORD *)(v85 + 20);
            if ( (v93 & 8) != 0 )
            {
              _XMM0.m128i_i64[0] = *(_QWORD *)v85;
            }
            else if ( (v93 & 0x24) != 0 )
            {
              *(double *)_XMM0.m128i_i64 = (double)(int)*(_QWORD *)v85;
            }
            else if ( (v93 & 0x12) != 0 )
            {
              *(double *)_XMM0.m128i_i64 = memRealValue(v85, v12, v8, v7);
            }
            else
            {
              _XMM0.m128i_i64[0] = 0;
            }
            v12 = (unsigned int)*v17 - 106;
            if ( *v17 == 106 )
            {
              *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 + v92;
            }
            else
            {
              v12 = (unsigned int)*v17 - 107;
              if ( *v17 == 107 )
              {
                *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 - v92;
              }
              else
              {
                v12 = (unsigned int)*v17 - 108;
                if ( *v17 == 108 )
                {
                  *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 * v92;
                }
                else if ( *v17 == 109 )
                {
                  if ( v92 == 0.0 )
                    goto LABEL_245;
                  *(double *)_XMM0.m128i_i64 = *(double *)_XMM0.m128i_i64 / v92;
                }
                else
                {
                  v94 = sqlite3_value_int64(v83, v12, v8);
                  v97 = sqlite3_value_int64(v85, v95, v96);
                  if ( !v94 )
                    goto LABEL_245;
                  if ( v94 == -1 )
                    v94 = 1;
                  v12 = v97 % v94;
                  *(double *)_XMM0.m128i_i64 = (double)(int)(v97 % v94);
                }
              }
            }
            LOBYTE(v12) = (_XMM0.m128i_i64[0] & 0xFFFFFFFFFFFFFLL) != 0;
            if ( ((unsigned __int8)v12 & ((_XMM0.m128i_i64[0] & 0x7FF0000000000000LL) == 0x7FF0000000000000LL)) == 0 )
            {
              *(_QWORD *)v86 = _XMM0.m128i_i64[0];
              nn = *(unsigned __int16 *)(v86 + 20);
              LOWORD(nn) = nn & 0xF240 | 8;
              *(_WORD *)(v86 + 20) = nn;
              v2 = v796;
              goto LABEL_67;
            }
            goto LABEL_245;
          }
          if ( v7 == 0x8000000000000000uLL )
          {
            if ( v8 < 0 )
            {
              v90 = v8 + 0x8000000000000000uLL;
              goto LABEL_207;
            }
            goto LABEL_217;
          }
          v7 = -v7;
          if ( v7 < 0 )
          {
            if ( v8 < 0 && (__int64)(0x8000000000000001uLL - v8) > v7 + 1 )
              goto LABEL_217;
          }
          else if ( v8 > 0 && 0x7FFFFFFFFFFFFFFFLL - v8 < v7 )
          {
            goto LABEL_217;
          }
        }
        v90 = v7 + v8;
        goto LABEL_207;
      case 111:
        v74 = v5 + 56LL * *((int *)v17 + 1);
        v75 = *(_WORD *)(v74 + 20);
        v76 = v5 + 56LL * *((int *)v791 + 2);
        v77 = v5 + 56LL * *((int *)v791 + 3);
        if ( ((*(_BYTE *)(v76 + 20) | (unsigned __int8)v75) & 1) != 0 )
        {
          nn = 36864;
          if ( (*(_WORD *)(v77 + 20) & 0x9000) == 0 )
          {
            v3 = 0;
            v14 = v793;
            *(_WORD *)(v77 + 20) = 1;
            v10 = v805;
            v17 = v791 + 24;
            continue;
          }
          nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v791 + 3), 0x180000000uLL, v8);
          v3 = 0;
          goto LABEL_67;
        }
        if ( (v75 & 0x12) != 0 )
        {
          if ( (v75 & 0x400) == 0 )
            goto LABEL_148;
          v78 = sqlite3VdbeMemExpandBlob(v5 + 56LL * *((int *)v791 + 1), 0x180000000uLL, v8);
        }
        else
        {
          v78 = sqlite3VdbeMemStringify(v5 + 56LL * *((int *)v791 + 1), v9, 0, v7);
        }
        if ( v78 )
          goto LABEL_82;
        v9 = v788;
        v75 = *(_WORD *)(v74 + 20) & 0xFFFD;
LABEL_148:
        v79 = *(_WORD *)(v76 + 20);
        if ( (v79 & 0x12) != 0 )
        {
          if ( (v79 & 0x400) == 0 )
          {
LABEL_154:
            v81 = *(_DWORD *)(v74 + 16) + *(_DWORD *)(v76 + 16);
            v82 = v81;
            if ( v81 > *(_DWORD *)(v796 + 136) )
            {
              v2 = v796;
              goto LABEL_1866;
            }
            _mm_lfence();
            if ( (unsigned int)sqlite3VdbeMemGrow(v77, (unsigned int)(v81 + 2), v77 == v76, v7) )
              goto LABEL_1927;
            *(_WORD *)(v77 + 20) &= 0xF242u;
            *(_WORD *)(v77 + 20) |= 2u;
            if ( v77 != v76 )
            {
              memmove(*(void **)(v77 + 8), *(const void **)(v76 + 8), *(int *)(v76 + 16));
              *(_WORD *)(v76 + 20) = v79;
            }
            memmove((void *)(*(_QWORD *)(v77 + 8) + *(int *)(v76 + 16)), *(const void **)(v74 + 8), *(int *)(v74 + 16));
            v9 = v788;
            *(_WORD *)(v74 + 20) = v75;
            if ( v788 > 1u )
              v82 &= ~1uLL;
            v7 = Table;
            *(_BYTE *)(v82 + *(_QWORD *)(v77 + 8)) = 0;
            *(_BYTE *)(*(_QWORD *)(v77 + 8) + v82 + 1) = 0;
            nn = 512;
            *(_WORD *)(v77 + 20) |= 0x200u;
            *(_DWORD *)(v77 + 16) = v82;
            v2 = v796;
            *(_BYTE *)(v77 + 22) = v788;
LABEL_161:
            v3 = 0;
            goto LABEL_162;
          }
          v80 = sqlite3VdbeMemExpandBlob(v76, v12, v8);
        }
        else
        {
          v80 = sqlite3VdbeMemStringify(v76, v9, 0, v7);
        }
        if ( v80 )
          goto LABEL_82;
        v79 = *(_WORD *)(v76 + 20) & 0xFFFD;
        goto LABEL_154;
      case 112:
      case 113:
        v307 = v17;
LABEL_831:
        if ( (v6[25] & 3) == 1 )
        {
          LODWORD(v7) = 516;
          goto LABEL_288;
        }
        v309 = 0;
        v310 = *((unsigned int *)v307 + 2);
        v311 = 0;
        v312 = *((_DWORD *)v307 + 3);
        v313 = *(_QWORD *)(v796 + 32);
        v314 = 32LL * v312;
        v315 = *(_QWORD *)(v314 + v313 + 8);
        if ( (_BYTE)v18 == 113 )
        {
          v316 = *((_WORD *)v307 + 1) & 8 | 4;
          v317 = *(_BYTE *)(*(_QWORD *)(v314 + v313 + 24) + 112LL);
          if ( v317 < *((_BYTE *)a1 + 197) )
            *((_BYTE *)a1 + 197) = v317;
        }
        else
        {
          v316 = 0;
        }
        if ( (v307[2] & 0x10) != 0 )
        {
          v318 = (_DWORD *)(v5 + 56 * v310);
          sqlite3VdbeMemIntegerify(v318);
          v307 = v791;
          LODWORD(v310) = *v318;
        }
        v319 = v307[1];
        if ( v319 == 0xF8 )
        {
          v311 = *((_QWORD *)v307 + 2);
          v309 = *(unsigned __int16 *)(v311 + 8);
        }
        else if ( v319 == 0xFD )
        {
          v309 = *((_DWORD *)v307 + 4);
        }
        Cursor = allocateCursor(a1, *((unsigned int *)v791 + 1), v309, 0);
        v308 = Cursor;
        if ( Cursor )
        {
          *(_BYTE *)(Cursor + 1) = v312;
          *(_BYTE *)(Cursor + 2) = 1;
          *(_DWORD *)(Cursor + 8) |= 4u;
          *(_DWORD *)(Cursor + 68) = v310;
          v321 = btreeCursor(v315, v310, v316, v311, *(_QWORD *)(Cursor + 48));
          v6 = a1;
          v7 = v321;
          *(_QWORD *)(v308 + 56) = v311;
          v2 = v796;
          Table = v321;
          *(_BYTE *)(v308 + 4) = v791[1] != 0xF8;
          v3 = 0;
LABEL_844:
          nn = *(_QWORD *)(v308 + 48);
          *(_BYTE *)(nn + 3) = v791[2] & 3;
LABEL_845:
          if ( (_DWORD)v7 )
            goto LABEL_289;
          v17 = v791;
          v5 = v794;
          v9 = v788;
          goto LABEL_164;
        }
        goto LABEL_544;
      case 114:
        v153 = v5 + 56LL * *((int *)v17 + 1);
        nn = 36864;
        v154 = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v154 + 20) & 0x9000) != 0 )
        {
          nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 2), 0x180000000uLL, v8);
          v7 = Table;
          v12 = 0x180000000uLL;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          *(_WORD *)(v154 + 20) = 1;
        }
        if ( (*(_BYTE *)(v153 + 20) & 1) != 0 )
          goto LABEL_93;
        *(_WORD *)(v154 + 20) = 4;
        nn = ~sqlite3_value_int64(v153, 0x180000000uLL, v8);
        *(_QWORD *)v154 = nn;
        goto LABEL_67;
      case 115:
        v322 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 2));
        v323 = allocateCursor(v6, *((unsigned int *)v17 + 1), (unsigned int)*(__int16 *)(v322 + 72), 0);
        if ( !v323 )
          goto LABEL_82;
        *(_BYTE *)(v323 + 2) = 1;
        *(_DWORD *)(v323 + 8) |= 1u;
        *(_QWORD *)(v323 + 56) = *(_QWORD *)(v322 + 56);
        *(_BYTE *)(v323 + 4) = *(_BYTE *)(v322 + 4);
        *(_DWORD *)(v323 + 68) = *(_DWORD *)(v322 + 68);
        v324 = *(_DWORD *)(v323 + 8) ^ (*(_DWORD *)(v322 + 8) ^ *(_DWORD *)(v323 + 8)) & 4;
        *(_DWORD *)(v323 + 8) = v324;
        *(_QWORD *)(v323 + 16) = *(_QWORD *)(v322 + 16);
        *(_DWORD *)(v323 + 8) = v324 | 8;
        *(_DWORD *)(v322 + 8) |= 8u;
        nn = btreeCursor(
               *(_QWORD *)(v323 + 16),
               *(_DWORD *)(v323 + 68),
               4,
               *(_QWORD *)(v323 + 56),
               *(_QWORD *)(v323 + 48));
        v5 = v794;
        v7 = (unsigned int)nn;
        v9 = v788;
        Table = nn;
        goto LABEL_165;
      case 116:
      case 118:
        v325 = *((int *)v17 + 3);
        if ( (int)v325 > 0 )
        {
          *(_DWORD *)(56 * v325 + v5 + 16) = 0;
          *(_QWORD *)(56LL * *((int *)v17 + 3) + v5 + 8) = &byte_1802990D8;
        }
        v326 = *((int *)v17 + 1);
        v327 = *(_QWORD *)(v6[15] + 8 * v326);
        if ( v327 && (*(_BYTE *)(v327 + 8) & 8) == 0 && *((_DWORD *)v17 + 2) <= *(__int16 *)(v327 + 72) )
        {
          *(_QWORD *)(v327 + 24) = 0;
          *(_DWORD *)(v327 + 32) = 0;
          nn = sqlite3BtreeClearTable(*(_QWORD *)(v327 + 16), *(unsigned int *)(v327 + 68), 0);
          Table = nn;
          v7 = (unsigned int)nn;
          LODWORD(v875) = nn;
          if ( (_DWORD)nn )
            goto LABEL_289;
          v5 = v794;
          v9 = v788;
          *(_BYTE *)(v327 + 2) = 1;
          goto LABEL_165;
        }
        v328 = allocateCursor(v6, v326, *((unsigned int *)v17 + 2), 0);
        v329 = v328;
        if ( !v328 )
          goto LABEL_82;
        *(_DWORD *)(v328 + 8) |= 1u;
        Table = sqlite3BtreeOpen(*(_QWORD *)v2, 0, v2, v328 + 16, *((unsigned __int16 *)v17 + 1) | 5u, 1054);
        LODWORD(v7) = Table;
        if ( Table )
          goto LABEL_289;
        v330 = *(_QWORD *)(v329 + 16);
        if ( *(_BYTE *)(v330 + 17) || *(_BYTE *)(v330 + 16) < 2u )
        {
          v333 = btreeBeginTrans(v330, 1, 0, Table);
          v7 = v333;
          Table = v333;
        }
        else
        {
          v331 = *(_QWORD *)(v330 + 8);
          if ( *(_DWORD *)(*(_QWORD *)v330 + 736LL) <= *(_DWORD *)(*(_QWORD *)v331 + 128LL)
            || *(_BYTE *)(*(_QWORD *)v331 + 10LL) == (_BYTE)Table )
          {
            v7 = 0;
            Table = 0;
          }
          else
          {
            _mm_lfence();
            v332 = ((__int64 (*)(void))pagerOpenSavepoint)();
            v7 = v332;
            Table = v332;
          }
        }
        if ( !(_DWORD)v7 )
        {
          v334 = *((_QWORD *)v17 + 2);
          *(_QWORD *)(v329 + 56) = v334;
          if ( v334 )
          {
            Table = btreeCreateTable(*(_QWORD *)(v329 + 16), v329 + 68, *((unsigned __int16 *)v17 + 1) | 2u);
            v7 = Table;
            if ( !Table )
            {
              v335 = btreeCursor(*(_QWORD *)(v329 + 16), *(_DWORD *)(v329 + 68), 4, v334, *(_QWORD *)(v329 + 48));
              v7 = v335;
              Table = v335;
            }
            *(_BYTE *)(v329 + 4) = 0;
          }
          else
          {
            *(_DWORD *)(v329 + 68) = 1;
            v336 = btreeCursor(*(_QWORD *)(v329 + 16), 1, 4, 0, *(_QWORD *)(v329 + 48));
            v7 = v336;
            Table = v336;
            *(_BYTE *)(v329 + 4) = 1;
          }
        }
        v337 = 0;
        if ( *((_WORD *)v17 + 1) != 8 )
          v337 = 4;
        nn = *(_DWORD *)(v329 + 8) & 0xFFFFFFFB;
        *(_DWORD *)(v329 + 8) = nn | v337;
        if ( (_DWORD)v7 )
        {
          sqlite3BtreeClose(*(_QWORD *)(v329 + 16));
          LODWORD(v7) = Table;
          goto LABEL_289;
        }
        v14 = v793;
        v5 = v794;
        v9 = v788;
        *(_BYTE *)(v329 + 2) = 1;
        goto LABEL_165;
      case 117:
        v37 = v17;
        v38 = *((int *)v17 + 2);
        v39 = v6[13] + 56 * v38;
        if ( (*(_WORD *)(v39 + 20) & 0x9000) != 0 )
        {
          v40 = out2PrereleaseWithClear(v6[13] + 56 * v38, 0x180000000uLL);
          v37 = v17;
          v39 = v40;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(v39 + 20) = 4;
        }
        v41 = *((_QWORD *)v37 + 2);
        if ( v41 )
        {
          v43 = strlen(*((const char **)v37 + 2));
          v37 = v17;
          v42 = v43 & 0x3FFFFFFF;
          v9 = v788;
        }
        else
        {
          v42 = 0;
        }
        *((_DWORD *)v37 + 1) = v42;
        if ( v9 == 1 )
          goto LABEL_50;
        LOBYTE(v37) = 1;
        Table = sqlite3VdbeMemSetStr(v39, v41, -1, v37, 0);
        if ( Table )
          goto LABEL_1866;
        if ( (*(_BYTE *)(v39 + 20) & 2) != 0 )
        {
          if ( *(_BYTE *)(v39 + 22) != v788 && (unsigned int)sqlite3VdbeMemTranslate(v39, v788) )
            goto LABEL_82;
        }
        else
        {
          *(_BYTE *)(v39 + 22) = v788;
        }
        v37 = v17;
        v3 = 0;
        *(_DWORD *)(v39 + 32) = 0;
        *(_WORD *)(v39 + 20) |= 0x2000u;
        if ( v17[1] == 0xFA && *((_QWORD *)v17 + 2) )
        {
          sqlite3DbFreeNN(v2);
          v37 = v17;
        }
        v9 = v788;
        v37[1] = -6;
        *((_QWORD *)v37 + 2) = *(_QWORD *)(v39 + 8);
        v42 = *(_DWORD *)(v39 + 16);
        *((_DWORD *)v37 + 1) = v42;
LABEL_50:
        if ( v42 <= *(_DWORD *)(v2 + 136) )
        {
          v14 = v793;
          *v37 = 73;
LABEL_53:
          v44 = *((int *)v37 + 2);
          v45 = v6[13] + 56 * v44;
          if ( (*(_WORD *)(v45 + 20) & 0x9000) != 0 )
          {
            v46 = out2PrereleaseWithClear(v6[13] + 56 * v44, v45);
            v37 = v17;
            v45 = v46;
            v9 = v788;
          }
          v5 = v794;
          *(_WORD *)(v45 + 20) = 8706;
          *(_QWORD *)(v45 + 8) = *((_QWORD *)v37 + 2);
          *(_DWORD *)(v45 + 16) = *((_DWORD *)v37 + 1);
          *(_BYTE *)(v45 + 22) = v9;
          nn = *((int *)v37 + 3);
          if ( (int)nn <= 0 || (v47 = 56 * nn, nn = *((unsigned __int16 *)v37 + 1), *(_QWORD *)(v47 + v794) != nn) )
          {
LABEL_1663:
            v7 = Table;
            goto LABEL_164;
          }
          v7 = Table;
          *(_WORD *)(v45 + 20) = 8720;
          goto LABEL_165;
        }
        goto LABEL_1866;
      case 119:
        LOBYTE(v7) = 1;
        v338 = allocateCursor(v6, *((unsigned int *)v17 + 1), *((unsigned int *)v17 + 2), v7);
        if ( !v338 )
          goto LABEL_82;
        *(_QWORD *)(v338 + 56) = *((_QWORD *)v17 + 2);
        nn = sqlite3VdbeSorterInit(v2, *((unsigned int *)v17 + 3), v338);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 120:
        v339 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v340 = *(_QWORD *)(v339 + 24);
        nn = v340 + 1;
        *(_QWORD *)(v339 + 24) = v340 + 1;
        if ( !v340 )
          goto LABEL_423;
        goto LABEL_166;
      case 121:
        LOBYTE(v7) = 3;
        nn = allocateCursor(v6, *((unsigned int *)v17 + 1), *((unsigned int *)v17 + 3), v7);
        if ( !nn )
          goto LABEL_82;
        v7 = Table;
        v5 = v794;
        v9 = v788;
        *(_BYTE *)(nn + 2) = 1;
        *(_DWORD *)(nn + 36) = *((_DWORD *)v17 + 2);
        *(_BYTE *)(nn + 4) = 1;
        *(_QWORD *)(nn + 48) = &byte_1803DC744;
        goto LABEL_165;
      case 122:
        v341 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        if ( v341 )
        {
          sqlite3VdbeFreeCursorNN(v6, v341, v8, v7);
          v7 = Table;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        nn = v6[15];
        *(_QWORD *)(nn + 8LL * *((int *)v17 + 1)) = 0;
        goto LABEL_30;
      case 124:
        v362 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 7));
        nn = *(_QWORD *)(v362 + 48);
        if ( *(_BYTE *)nn )
        {
LABEL_93:
          v14 = v793;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v810[0] = *(_QWORD *)(v362 + 56);
        v812 = 0;
        v363 = *((_DWORD *)v17 + 1);
        v811 = *((_WORD *)v17 + 20);
        v810[1] = v5 + 56LL * *((int *)v17 + 9);
        while ( 1 )
        {
          while ( 1 )
          {
            v364 = *(_QWORD *)(v362 + 48);
            getCellInfo(v364, v12, v8);
            v365 = *(_DWORD *)(v364 + 64);
            if ( v365 - 1 > 0x7FFFFFFE )
            {
              sqlite3_log(
                11,
                "%s at line %d of [%.10s]",
                "database corruption",
                90371,
                "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
              LODWORD(v7) = 11;
              Table = 11;
              goto LABEL_289;
            }
            v841 = 0;
            v842 = v2;
            v843 = 0;
            v366 = *(unsigned __int16 *)(v364 + 68);
            v367 = *(_DWORD *)(*(_QWORD *)(v364 + 136) + 88LL) - *(_DWORD *)(v364 + 56);
            if ( v366 > v367 )
            {
              v366 = *(_DWORD *)(*(_QWORD *)(v364 + 136) + 88LL) - *(_DWORD *)(v364 + 56);
              if ( v367 < 0 )
                v366 = 0;
            }
            v368 = *(_QWORD *)(v364 + 56);
            v839 = v368;
            if ( v365 > v366 )
            {
              _mm_lfence();
              Table = sqlite3VdbeMemFromBtree(v364, 0, v365, v838);
              LODWORD(v7) = Table;
              if ( Table )
                goto LABEL_289;
              v365 = v840;
              v368 = v839;
            }
            else
            {
              v840 = v365;
              v841 = 16400;
            }
            nn = sqlite3VdbeRecordCompareWithSkip(v365, v368, v810, 0);
            v371 = nn;
            if ( v843 )
              nn = vdbeMemClear(v838);
            Table = 0;
            v7 = 0;
            v372 = v371 < 0;
            if ( v371 > 0 )
            {
              if ( !*((_WORD *)v17 + 1) )
                goto LABEL_969;
              v372 = v371 < 0;
            }
            if ( !v372 )
            {
              v5 = v794;
              v14 = v793;
              Table = 0;
              goto LABEL_423;
            }
            if ( v363 <= 0 )
            {
              v5 = v794;
              v9 = v788;
              Table = 0;
              goto LABEL_164;
            }
            *(_DWORD *)(v362 + 32) = 0;
            --v363;
            v373 = *(_QWORD *)(v362 + 48);
            *(_WORD *)(v373 + 70) = 0;
            *(_BYTE *)(v373 + 1) &= 0xF9u;
            if ( !*(_BYTE *)v373 )
              break;
            v374 = btreeNext(v373, v369, v370, 0);
LABEL_966:
            Table = v374;
            LODWORD(v7) = v374;
            if ( v374 )
            {
              if ( v374 != 101 )
                goto LABEL_289;
              v7 = 0;
              Table = 0;
LABEL_969:
              v5 = v794;
              v17 += 24;
              v14 = v793;
LABEL_423:
              v9 = v788;
              nn = *((_DWORD *)v17 + 2) - 1;
              v3 = 0;
              v17 = (unsigned __int8 *)(v14 + 24 * nn);
              v2 = v796;
              goto LABEL_165;
            }
          }
          v8 = *(unsigned __int16 *)(v373 + 86);
          v12 = *(_QWORD *)(v373 + 136);
          *(_WORD *)(v373 + 86) = v8 + 1;
          if ( (unsigned __int16)(v8 + 1) >= *(_WORD *)(v12 + 24) )
          {
            *(_WORD *)(v373 + 86) = v8;
            v374 = btreeNext(v373, v12, v8, 0);
            goto LABEL_966;
          }
          if ( !*(_BYTE *)(v12 + 8) )
          {
            v374 = moveToLeftmost(v373);
            goto LABEL_966;
          }
        }
      case 125:
        v375 = *((_DWORD *)v17 + 2);
        nn = v6[15];
        v376 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        v377 = *(unsigned __int16 *)(v376 + 12);
        if ( v377 < v375 )
        {
          *(_WORD *)(v376 + 12) = v375;
          goto LABEL_165;
        }
        v8 = v792;
        nn = *((unsigned int *)v17 + 3);
        if ( v377 <= (int)nn )
          goto LABEL_166;
        *(_WORD *)(v376 + 12) = nn;
        v12 = 0x180000000uLL;
        v10 = v805;
        v17 += 24;
        continue;
      case 126:
        v391 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v391 + 20) & 0x9000) != 0 )
        {
          v392 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v391);
          v7 = Table;
          v391 = v392;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          *(_WORD *)(v391 + 20) = 4;
        }
        *(_QWORD *)v391 = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 24LL);
        nn = v6[15];
        ++*(_QWORD *)(*(_QWORD *)(nn + 8LL * *((int *)v17 + 1)) + 24LL);
        v12 = 0x180000000uLL;
        v10 = v805;
        v17 += 24;
        continue;
      case 127:
        v393 = 0;
        v875 = 0;
        v394 = 0;
        v798 = 0;
        v395 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v395 + 20) & 0x9000) != 0 )
          v395 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
        else
          *(_WORD *)(v395 + 20) = 4;
        v396 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        if ( (*(_BYTE *)(v396 + 8) & 2) != 0 )
          goto LABEL_1026;
        v397 = *(_BYTE **)(v396 + 48);
        if ( *v397 || (v397[1] & 8) == 0 )
        {
          Table = btreeLast(v397, &v798);
          LODWORD(v7) = Table;
          if ( Table )
            goto LABEL_1046;
          v394 = v798;
        }
        else
        {
          Table = 0;
          v3 = 0;
        }
        if ( v394 )
        {
          v393 = 1;
          v875 = 1;
        }
        else
        {
          v401 = *(_QWORD *)(v396 + 48);
          getCellInfo(v401, v12, v8);
          v393 = *(_QWORD *)(v401 + 48);
          v875 = v393;
          if ( v393 == 0x7FFFFFFFFFFFFFFFLL )
            *(_DWORD *)(v396 + 8) |= 2u;
          else
            v875 = ++v393;
        }
LABEL_1026:
        nn = *((int *)v17 + 3);
        if ( (_DWORD)nn )
        {
          v398 = v6[33];
          if ( v398 )
          {
            for ( i1 = *(_QWORD *)(v398 + 8); i1; i1 = *(_QWORD *)(i1 + 8) )
              v398 = i1;
            v400 = (__int64 *)(*(_QWORD *)(v398 + 24) + 56LL * *((int *)v17 + 3));
          }
          else
          {
            v400 = (__int64 *)(v794 + 56 * nn);
          }
          sqlite3VdbeMemIntegerify(v400);
          if ( *v400 == 0x7FFFFFFFFFFFFFFFLL || (*(_BYTE *)(v396 + 8) & 2) != 0 )
          {
LABEL_1045:
            LODWORD(v7) = 13;
            Table = 13;
            goto LABEL_1046;
          }
          nn = *v400 + 1;
          if ( v393 < nn )
            v393 = *v400 + 1;
          v875 = v393;
          *v400 = v393;
        }
        if ( (*(_BYTE *)(v396 + 8) & 2) == 0 )
        {
          v7 = Table;
LABEL_1048:
          v5 = v794;
          v9 = v788;
          *(_BYTE *)(v396 + 3) = 0;
          *(_DWORD *)(v396 + 32) = 0;
          *(_QWORD *)v395 = v393;
          v2 = v796;
          goto LABEL_164;
        }
        v402 = 0;
        while ( 1 )
        {
          sqlite3_randomness(8, &v875);
          v403 = *(_QWORD *)(v396 + 48);
          v393 = (v875 & 0x3FFFFFFFFFFFFFFFLL) + 1;
          v875 = v393;
          nn = sqlite3BtreeTableMoveto(v403, v393, 0, &v798);
          Table = nn;
          v7 = (unsigned int)nn;
          if ( (_DWORD)nn )
            goto LABEL_1046;
          if ( v798 )
            goto LABEL_1048;
          if ( ++v402 >= 100 )
            goto LABEL_1045;
        }
      case 128:
        v404 = (int *)(v5 + 56LL * *((int *)v17 + 2));
        v405 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v851 = *(_QWORD *)(56LL * *((int *)v17 + 3) + v5);
        if ( v17[1] == 0xFB && *(_QWORD *)(v2 + 304) )
        {
          v406 = (_QWORD *)*((_QWORD *)v17 + 2);
          v407 = *(_QWORD *)(32LL * *(char *)(v405 + 1) + *(_QWORD *)(v2 + 32));
        }
        else
        {
          v406 = 0;
          v407 = 0;
        }
        if ( (v17[2] & 1) != 0 )
        {
          ++v6[7];
          if ( (v17[2] & 0x20) != 0 )
            *(_QWORD *)(v2 + 56) = v851;
        }
        v852 = *((_QWORD *)v404 + 1);
        v853 = v404[4];
        if ( (v17[2] & 0x10) != 0 )
          v408 = *(unsigned int *)(v405 + 36);
        else
          v408 = 0;
        if ( (v404[5] & 0x400) != 0 )
          v854 = *v404;
        else
          v854 = 0;
        v850 = 0;
        nn = sqlite3BtreeInsert(*(_QWORD *)(v405 + 48), &v850, *((_WORD *)v17 + 1) & 0x8A, v408);
        ++v802;
        v7 = (unsigned int)nn;
        *(_BYTE *)(v405 + 3) = 0;
        Table = nn;
        *(_DWORD *)(v405 + 32) = 0;
        if ( (_DWORD)nn )
          goto LABEL_289;
        if ( !v406 )
          goto LABEL_1122;
        v409 = 18;
        if ( (v17[2] & 4) != 0 )
          v409 = 23;
        nn = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64))(v2 + 304))(
               *(_QWORD *)(v2 + 296),
               v409,
               v407,
               *v406,
               v851);
        goto LABEL_67;
      case 129:
        v410 = *((int *)v17 + 3);
        if ( (_DWORD)v410 )
          v411 = *(_QWORD *)(56 * v410 + v5);
        else
          v411 = 0;
        nn = sqlite3BtreeTransferRow(
               *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL),
               *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 2)) + 48LL),
               v411);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 130:
        v412 = v17;
        v413 = *((_DWORD *)v17 + 2);
        v414 = *(_QWORD *)(v6[15] + 8LL * *((int *)v791 + 1));
        if ( v791[1] == 0xFB && *(_QWORD *)(v2 + 304) )
        {
          v415 = *((_QWORD *)v791 + 2);
          v416 = *(_QWORD *)(32LL * *(char *)(v414 + 1) + *(_QWORD *)(v2 + 32));
          if ( (v791[2] & 2) != 0 && *(_BYTE *)(v414 + 4) )
          {
            v417 = *(_QWORD *)(v414 + 48);
            getCellInfo(v417, 0x180000000uLL, v8);
            v412 = v791;
            *(_QWORD *)(v414 + 80) = *(_QWORD *)(v417 + 48);
          }
        }
        else
        {
          v416 = 0;
          v415 = 0;
        }
        nn = sqlite3BtreeDelete(*(_QWORD *)(v414 + 48), v412[2], v8);
        ++v802;
        v7 = (unsigned int)nn;
        *(_DWORD *)(v414 + 32) = 0;
        Table = nn;
        *(_DWORD *)(v414 + 36) = 0;
        if ( (_DWORD)nn )
          goto LABEL_1046;
        if ( (v413 & 1) != 0 )
        {
          ++v6[7];
          v418 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD))(v796 + 304);
          if ( v418 && v415 && *(char *)(v415 + 48) >= 0 )
          {
            v419 = v416;
            v2 = v796;
            nn = v418(*(_QWORD *)(v796 + 296), 9, v419, *(_QWORD *)v415, *(_QWORD *)(v414 + 80));
            goto LABEL_67;
          }
          v17 = v791;
          v2 = v796;
          v5 = v794;
          v3 = 0;
          v9 = v788;
        }
        else
        {
          v2 = v796;
          v3 = 0;
          v17 = v791;
          v5 = v794;
          v9 = v788;
        }
        goto LABEL_164;
      case 131:
        nn = v6[7];
        *(_QWORD *)(v2 + 120) = nn;
        *(_QWORD *)(v2 + 128) += nn;
        v6[7] = 0;
        v10 = v805;
        v17 += 24;
        continue;
      case 132:
        v420 = *((_DWORD *)v17 + 4);
        v421 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v422 = *(_QWORD *)(v421 + 48);
        v423 = *(_QWORD *)(v421 + 56);
        v424 = v5 + 56LL * *((int *)v17 + 3);
        v425 = *(_QWORD *)(v422 + 48);
        if ( v425 )
          goto LABEL_1088;
        v426 = sqlite3VdbeAllocUnpackedRecord(*(_QWORD *)(v421 + 56), v421, v8);
        *(_QWORD *)(v422 + 48) = v426;
        v425 = v426;
        if ( !v426 )
        {
          v2 = v796;
          LODWORD(v7) = 7;
          goto LABEL_288;
        }
        *(_WORD *)(v426 + 28) = v420;
LABEL_1088:
        if ( *(_BYTE *)(v422 + 88) )
        {
          if ( *(_BYTE *)(v422 + 89) )
            v427 = *(_QWORD *)(v422 + 16);
          else
            v427 = *(_QWORD *)(*(_QWORD *)(v422 + 24) + 24LL)
                 + 80LL * *(int *)(*(_QWORD *)(*(_QWORD *)(v422 + 24) + 16LL) + 4LL);
          v428 = *(unsigned int **)(v427 + 40);
          v429 = (unsigned int *)(v427 + 20);
        }
        else
        {
          v429 = *(unsigned int **)(v422 + 56);
          v428 = v429 + 4;
        }
        sqlite3VdbeRecordUnpack(v423, *v429, v428, v425);
        v430 = 0;
        if ( v420 <= 0 )
          goto LABEL_1098;
        v431 = (_BYTE *)(*(_QWORD *)(v425 + 8) + 20LL);
        do
        {
          if ( (*v431 & 1) != 0 )
          {
            v17 = v791;
            v7 = 0;
            v5 = v794;
            v14 = v793;
            Table = 0;
            goto LABEL_423;
          }
          ++v430;
          v431 += 56;
        }
        while ( v430 < v420 );
LABEL_1098:
        nn = sqlite3VdbeRecordCompareWithSkip(*(unsigned int *)(v424 + 16), *(_QWORD *)(v424 + 8), v425, 0);
        Table = 0;
        v7 = 0;
        if ( !(_DWORD)nn )
          goto LABEL_248;
        v17 = v791;
        v5 = v794;
        v14 = v793;
        goto LABEL_423;
      case 133:
        v432 = v5 + 56LL * *((int *)v17 + 2);
        v433 = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL);
        if ( *(_BYTE *)(v433 + 88) )
        {
          if ( *(_BYTE *)(v433 + 89) )
            v434 = *(_QWORD *)(v433 + 16);
          else
            v434 = *(_QWORD *)(*(_QWORD *)(v433 + 24) + 24LL)
                 + 80LL * *(int *)(*(_QWORD *)(*(_QWORD *)(v433 + 24) + 16LL) + 4LL);
          v435 = *(const void **)(v434 + 40);
          v436 = (int *)(v434 + 20);
        }
        else
        {
          v436 = *(int **)(v433 + 56);
          v435 = v436 + 4;
        }
        v437 = *v436;
        if ( *(_DWORD *)(v432 + 32) >= (int)v437 )
        {
          *(_QWORD *)(v432 + 8) = *(_QWORD *)(v432 + 40);
          *(_WORD *)(v432 + 20) &= 0x2Du;
        }
        else
        {
          _mm_lfence();
          if ( (unsigned int)sqlite3VdbeMemGrow(v5 + 56LL * *((int *)v17 + 2), (unsigned int)v437, 0, v7) )
          {
            LODWORD(v7) = 7;
            goto LABEL_288;
          }
        }
        *(_DWORD *)(v432 + 16) = v437;
        *(_WORD *)(v432 + 20) &= 0xF250u;
        *(_WORD *)(v432 + 20) |= 0x10u;
        memmove(*(void **)(v432 + 8), v435, v437);
        v7 = 0;
        v5 = v794;
        v9 = v788;
        nn = v6[15];
        Table = 0;
        *(_DWORD *)(*(_QWORD *)(nn + 8LL * *((int *)v17 + 3)) + 32LL) = 0;
        goto LABEL_164;
      case 134:
        v438 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v438 + 20) & 0x9000) != 0 )
          v438 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
        else
          *(_WORD *)(v438 + 20) = 4;
        v439 = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL);
        getCellInfo(v439, v12, v8);
        v440 = *(unsigned int *)(v439 + 64);
        if ( (unsigned int)v440 > *(_DWORD *)(v2 + 136) )
          goto LABEL_1866;
        _mm_lfence();
        nn = sqlite3VdbeMemFromBtreeZeroOffset(v439, v440, v438);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        if ( *((_DWORD *)v17 + 3) )
          goto LABEL_1123;
        nn = 0x4000;
        if ( (*(_WORD *)(v438 + 20) & 0x4000) == 0 )
          goto LABEL_1123;
        nn = sqlite3VdbeMemMakeWriteable(v438, v441, v8, v7);
        if ( (_DWORD)nn )
          goto LABEL_82;
        v7 = 0;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 135:
        v442 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v442 + 20) & 0x9000) != 0 )
        {
          v443 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
          v7 = Table;
          v12 = 0x180000000uLL;
          v5 = v794;
          v442 = v443;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          *(_WORD *)(v442 + 20) = 4;
        }
        nn = v6[15];
        v444 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        if ( *(_BYTE *)(v444 + 2) )
        {
          *(_WORD *)(v442 + 20) = 1;
          v14 = v793;
          v10 = v805;
          v17 += 24;
          continue;
        }
        if ( *(_BYTE *)(v444 + 3) )
        {
          nn = *(_QWORD *)(v444 + 80);
          v5 = v794;
          v9 = v788;
          v878 = nn;
          *(_QWORD *)v442 = nn;
        }
        else
        {
          v445 = *(__int64 **)(v444 + 48);
          if ( *(_BYTE *)v444 == 2 )
          {
            v446 = *v445;
            Table = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD, __int64))(*(_QWORD *)*v445 + 96LL))(
                      v445,
                      &v878,
                      *(_QWORD *)(*(_QWORD *)*v445 + 96LL),
                      v7);
            sqlite3VtabImportErrmsg(v6, v446);
            v7 = Table;
            if ( Table )
              goto LABEL_289;
            nn = v878;
            v3 = 0;
            v5 = v794;
            v9 = v788;
            *(_QWORD *)v442 = v878;
          }
          else
          {
            if ( *(_BYTE *)v445 )
            {
              nn = sqlite3VdbeHandleMovedCursor(v444, 0x180000000uLL, v8, v7);
              Table = nn;
              v7 = (unsigned int)nn;
              if ( (_DWORD)nn )
                goto LABEL_289;
            }
            else
            {
              v7 = 0;
              Table = 0;
            }
            if ( *(_BYTE *)(v444 + 2) )
            {
              v5 = v794;
              v9 = v788;
              *(_WORD *)(v442 + 20) = 1;
            }
            else
            {
              v447 = *(_QWORD *)(v444 + 48);
              getCellInfo(v447, v12, v8);
              nn = *(_QWORD *)(v447 + 48);
              v7 = 0;
              v5 = v794;
              v9 = v788;
              v878 = nn;
              *(_QWORD *)v442 = nn;
            }
          }
        }
        goto LABEL_164;
      case 136:
        v448 = *((int *)v17 + 1);
        nn = *(_QWORD *)(v6[15] + 8 * v448);
        if ( nn )
          goto LABEL_1149;
        LOBYTE(v7) = 3;
        nn = allocateCursor(v6, v448, 1, v7);
        if ( !nn )
          goto LABEL_1928;
        v7 = Table;
        *(_DWORD *)(nn + 36) = 0;
        *(_BYTE *)(nn + 4) = 1;
        *(_DWORD *)(nn + 8) |= 8u;
        *(_QWORD *)(nn + 48) = &byte_1803DC744;
LABEL_1149:
        *(_BYTE *)(nn + 2) = 1;
        *(_DWORD *)(nn + 32) = 0;
        if ( *(_BYTE *)nn )
          goto LABEL_130;
        nn = sqlite3BtreeClearCursor(*(_QWORD *)(nn + 48), v448, v8);
        goto LABEL_129;
      case 138:
        v474 = v17;
        v475 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v476 = v5 + 56LL * *((int *)v17 + 2);
        if ( (v17[2] & 1) != 0 )
          ++v6[7];
        if ( (*(_WORD *)(v476 + 20) & 0x400) == 0 )
          goto LABEL_1228;
        Table = sqlite3VdbeMemExpandBlob(v476, 0x180000000uLL, v8);
        LODWORD(v7) = Table;
        if ( Table )
          goto LABEL_289;
        v474 = v17;
        v5 = v794;
LABEL_1228:
        v870[1] = *(int *)(v476 + 16);
        v870[0] = *(_QWORD *)(v476 + 8);
        v870[3] = v5 + 56LL * *((int *)v474 + 3);
        v871 = *((_WORD *)v474 + 8);
        v477 = *((_WORD *)v474 + 1);
        v478 = (v477 & 0x10) != 0 ? *(unsigned int *)(v475 + 36) : 0LL;
        nn = sqlite3BtreeInsert(*(_QWORD *)(v475 + 48), v870, v477 & 0x8A, v478);
        Table = nn;
        v7 = (unsigned int)nn;
        *(_DWORD *)(v475 + 32) = 0;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 139:
        v479 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v480 = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v480 + 20) & 0x400) != 0 )
        {
          Table = sqlite3VdbeMemExpandBlob(v5 + 56LL * *((int *)v17 + 2), 0x180000000uLL, v8);
          LODWORD(v7) = Table;
          if ( Table )
            goto LABEL_289;
        }
        nn = sqlite3VdbeSorterWrite(v479, v480, v8);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 140:
        v481 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v482 = *(_QWORD *)(v481 + 48);
        v867[0] = *(_QWORD *)(v481 + 56);
        v868 = *((_WORD *)v17 + 6);
        v869 = 0;
        v867[1] = v5 + 56LL * *((int *)v17 + 2);
        nn = sqlite3BtreeIndexMoveto(v482, v867, &v807);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        if ( v807 )
        {
          if ( *((_WORD *)v17 + 1) )
          {
            nn = *(_DWORD *)(v2 + 48) & 0x10000001;
            if ( nn != 1 )
            {
              Table = 779;
              sqlite3_log(
                779,
                "%s at line %d of [%.10s]",
                "index corruption",
                99932,
                "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
              LODWORD(v7) = 779;
              goto LABEL_289;
            }
          }
          v5 = v794;
          v9 = v788;
          *(_DWORD *)(v481 + 32) = 0;
          *(_DWORD *)(v481 + 36) = 0;
        }
        else
        {
          LOBYTE(v483) = 4;
          nn = sqlite3BtreeDelete(v482, v483, v8);
          Table = nn;
          v7 = (unsigned int)nn;
          if ( (_DWORD)nn )
            goto LABEL_289;
          v5 = v794;
          v9 = v788;
          *(_DWORD *)(v481 + 32) = 0;
          *(_DWORD *)(v481 + 36) = 0;
        }
        goto LABEL_164;
      case 141:
      case 142:
        v484 = *((int *)v17 + 1);
        v485 = *(_QWORD *)(v6[15] + 8 * v484);
        if ( **(_BYTE **)(v485 + 48) )
        {
          Table = sqlite3VdbeHandleMovedCursor(*(_QWORD *)(v6[15] + 8 * v484), 0x180000000uLL, v8, v7);
          v7 = Table;
          if ( Table )
            goto LABEL_289;
          v5 = v794;
          v12 = 0x180000000uLL;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          v7 = 0;
          Table = 0;
        }
        if ( !*(_BYTE *)(v485 + 2) )
        {
          v486 = *(_QWORD *)(v485 + 48);
          v801 = 0;
          Table = sqlite3VdbeIdxRowid(v2, v486, &v801, v7);
          v7 = Table;
          if ( Table )
            goto LABEL_289;
          if ( *v17 == 0x8D )
          {
            v5 = v794;
            v9 = v788;
            v487 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 3));
            v488 = v801;
            *(_BYTE *)(v487 + 2) = Table;
            *(_QWORD *)(v487 + 80) = v488;
            *(_BYTE *)(v487 + 3) = 1;
            *(_DWORD *)(v487 + 32) = 0;
            nn = *((_QWORD *)v17 + 2);
            *(_QWORD *)(v487 + 16) = nn;
            *(_QWORD *)(v487 + 40) = v485;
          }
          else
          {
            v489 = v6[13] + 56LL * *((int *)v17 + 2);
            if ( (*(_WORD *)(v489 + 20) & 0x9000) != 0 )
            {
              v490 = out2PrereleaseWithClear(v489, v489);
              v7 = 0;
              v491 = (_QWORD *)v490;
              nn = v801;
              v5 = v794;
              v9 = v788;
              *v491 = v801;
            }
            else
            {
              nn = v801;
              v5 = v794;
              v9 = v788;
              *(_WORD *)(v489 + 20) = 4;
              *(_QWORD *)v489 = nn;
            }
          }
          goto LABEL_165;
        }
        nn = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(nn + 20) & 0x9000) != 0 )
        {
LABEL_408:
          nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 2), 0x180000000uLL, v8);
          goto LABEL_129;
        }
        *(_WORD *)(nn + 20) = 1;
        v10 = v805;
        v17 += 24;
        continue;
      case 143:
        nn = v6[15];
        v492 = *(_QWORD *)(nn + 8LL * *((int *)v17 + 1));
        if ( !*(_BYTE *)(v492 + 3) )
        {
LABEL_71:
          v10 = v805;
          v17 += 24;
          continue;
        }
        nn = sqlite3VdbeFinishMoveto(v492, 0x180000000uLL, v8, v7);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 144:
        v502 = v17;
        v503 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v503 + 20) & 0x9000) != 0 )
        {
          v504 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
          v502 = v17;
          v503 = v504;
        }
        *(_WORD *)(v503 + 20) = 1;
        if ( *(_DWORD *)(v2 + 220) > *(_DWORD *)(v2 + 232) + 1 )
        {
          LODWORD(v7) = 6;
          *((_BYTE *)v6 + 196) = 2;
          Table = 6;
          goto LABEL_289;
        }
        v505 = *((_DWORD *)v502 + 3);
        v506 = *(_QWORD *)(v2 + 32);
        v507 = *((unsigned int *)v502 + 1);
        v508 = 32LL * v505;
        LODWORD(v875) = 0;
        nn = btreeDropTable(*(_QWORD *)(v508 + v506 + 8), v507, &v875);
        v509 = (int)v875;
        v7 = (unsigned int)nn;
        *(_WORD *)(v503 + 20) = 4;
        *(_QWORD *)v503 = v509;
        Table = nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        if ( !(_DWORD)v509 )
        {
          v14 = v793;
          v5 = v794;
          v9 = v788;
          goto LABEL_165;
        }
        v510 = *(_QWORD *)(v2 + 32);
        v511 = *((_DWORD *)v17 + 1);
        for ( i2 = *(_QWORD **)(*(_QWORD *)(v508 + v510 + 24) + 16LL); i2; i2 = (_QWORD *)*i2 )
        {
          v513 = i2[2];
          if ( *(_DWORD *)(v513 + 40) == (_DWORD)v509 )
            *(_DWORD *)(v513 + 40) = v511;
        }
        nn = *(_QWORD *)(v508 + v510 + 24);
        for ( i3 = *(_QWORD **)(nn + 40); i3; i3 = (_QWORD *)*i3 )
        {
          nn = i3[2];
          if ( *(_DWORD *)(nn + 88) == (_DWORD)v509 )
            *(_DWORD *)(nn + 88) = v511;
        }
        v800 = v505 + 1;
        goto LABEL_67;
      case 145:
        v877 = 0;
        nn = sqlite3BtreeClearTable(
               *(_QWORD *)(32LL * *((int *)v17 + 2) + *(_QWORD *)(v2 + 32) + 8),
               *((unsigned int *)v17 + 1),
               &v877);
        v7 = (unsigned int)nn;
        v5 = v794;
        Table = nn;
        if ( *((_DWORD *)v17 + 3) )
        {
          v6[7] += v877;
          nn = *((int *)v17 + 3);
          if ( (int)nn > 0 )
          {
            v515 = 56 * nn;
            nn = v877;
            *(_QWORD *)(v515 + v794) += v877;
          }
        }
        if ( (_DWORD)v7 )
          goto LABEL_289;
        v9 = v788;
        goto LABEL_165;
      case 146:
        v516 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        if ( *(_BYTE *)v516 == 1 )
        {
          nn = sqlite3VdbeSorterReset(v2, *(_QWORD *)(v516 + 48), v8, v7);
          goto LABEL_129;
        }
        nn = sqlite3BtreeClearTable(
               *(_QWORD *)(*(_QWORD *)(v516 + 48) + 8LL),
               *(unsigned int *)(*(_QWORD *)(v516 + 48) + 80LL),
               0);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 147:
        v517 = v17;
        v518 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v518 + 20) & 0x9000) != 0 )
        {
          v519 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
          v517 = v17;
          v518 = v519;
        }
        else
        {
          *(_WORD *)(v518 + 20) = 4;
        }
        v520 = *(_QWORD *)(v2 + 32);
        v521 = *((unsigned int *)v517 + 3);
        v522 = 32LL * *((int *)v517 + 1);
        LODWORD(v875) = 0;
        Table = btreeCreateTable(*(_QWORD *)(v522 + v520 + 8), &v875, v521);
        v7 = Table;
        if ( Table )
          goto LABEL_289;
        nn = (unsigned int)v875;
        v5 = v794;
        v9 = v788;
        *(_QWORD *)v518 = (unsigned int)v875;
        goto LABEL_165;
      case 148:
        ++*(_BYTE *)(v2 + 112);
        v817 = 0;
        v523 = *(_QWORD *)(v2 + 496);
        v524 = *(_BYTE *)(v2 + 110);
        v525 = *(_DWORD *)(v2 + 728);
        if ( (v17[4] & 1) != 0 )
        {
          *(_QWORD *)(v2 + 496) = 0;
          *(_BYTE *)(v2 + 110) = 0;
        }
        if ( (v17[4] & 2) != 0 )
          *(_DWORD *)(v2 + 728) = *((_DWORD *)v17 + 2);
        nn = sqlite3_exec(v2, *((_QWORD *)v17 + 2), 0, 0, (__int64)&v817);
        --*(_BYTE *)(v2 + 112);
        v7 = (unsigned int)nn;
        *(_QWORD *)(v2 + 496) = v523;
        *(_BYTE *)(v2 + 110) = v524;
        *(_DWORD *)(v2 + 728) = v525;
        Table = nn;
        if ( !v817 && !(_DWORD)nn )
          goto LABEL_68;
        sqlite3VdbeError(v6, "%s", v817);
        v526 = v817;
        if ( v817 )
        {
          if ( dword_1803379C0 )
          {
            if ( (_QWORD)xmmword_1803DC8D0 )
              xmmword_180337A40(xmmword_1803DC8D0);
            v527 = (*((__int64 (__fastcall **)(const char *))&xmmword_1803379F0 + 1))(v526);
            --qword_1803DC858;
            qword_1803DC810 -= v527;
            (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v526);
            if ( (_QWORD)xmmword_1803DC8D0 )
              xmmword_180337A50(xmmword_1803DC8D0);
          }
          else
          {
            (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v817);
          }
        }
        LODWORD(v7) = Table;
        v11 = v795;
        v4 = (unsigned __int8 *)v793;
        if ( Table != 7 )
          goto LABEL_291;
        goto LABEL_83;
      case 149:
        v528 = *((int *)v17 + 1);
        if ( *((_QWORD *)v17 + 2) )
        {
          v823[0] = v2;
          v823[1] = v6 + 21;
          v824 = v528;
          v826 = 0;
          v828 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(32 * v528 + *(_QWORD *)(v2 + 32) + 8) + 8LL) + 64LL);
          v529 = sqlite3MPrintf(
                   v2,
                   "SELECT*FROM\"%w\".%s WHERE %s ORDER BY rowid",
                   *(_QWORD *)(32 * v528 + *(_QWORD *)(v2 + 32)),
                   "sqlite_master",
                   *((_QWORD *)v17 + 2));
          if ( !v529 )
          {
            sqlite3ResetAllSchemasOfConnection(v2);
            goto LABEL_82;
          }
          *(_BYTE *)(v2 + 197) = 1;
          v825 = 0;
          v827 = 0;
          Table = sqlite3_exec(v2, v529, (unsigned int)sqlite3InitCallback, (unsigned int)v823, 0);
          if ( !Table )
          {
            Table = v825;
            if ( !v825 && !v827 )
            {
              sqlite3_log(
                11,
                "%s at line %d of [%.10s]",
                "database corruption",
                100430,
                "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
              Table = 11;
            }
          }
          nn = sqlite3DbFreeNN(v2);
          v7 = Table;
          v3 = 0;
          *(_BYTE *)(v2 + 197) = 0;
        }
        else
        {
          sqlite3SchemaClear(*(_QWORD *)(32 * v528 + *(_QWORD *)(v2 + 32) + 24), 0x180000000uLL, v8);
          *(_DWORD *)(v2 + 44) &= ~0x10u;
          nn = sqlite3InitOne(v2, (unsigned int)v528, v6 + 21, *((unsigned __int16 *)v17 + 1));
          *(_DWORD *)(v2 + 44) |= 1u;
          v7 = (unsigned int)nn;
          *((_DWORD *)v6 + 50) &= 0xFFFFFFFC;
          Table = nn;
        }
        if ( !(_DWORD)v7 )
          goto LABEL_130;
        sqlite3ResetAllSchemasOfConnection(v2);
        LODWORD(v7) = Table;
        v11 = v795;
        v4 = (unsigned __int8 *)v793;
        if ( Table != 7 )
          goto LABEL_1325;
        goto LABEL_83;
      case 150:
        nn = sqlite3AnalysisLoad(v2, *((unsigned int *)v17 + 1), v8, v7);
        Table = nn;
        v7 = (unsigned int)nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 151:
        nn = sqlite3HashInsert(
               *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 24) + 8LL,
               *((_QWORD *)v17 + 2),
               0);
        if ( nn )
        {
          if ( *(_QWORD *)(v2 + 760) || (v216 = *(_DWORD *)(nn + 44) == 1, --*(_DWORD *)(nn + 44), v216) )
            nn = deleteTable(v2, nn);
        }
        goto LABEL_1332;
      case 152:
        nn = sqlite3HashInsert(
               *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 24) + 32LL,
               *((_QWORD *)v17 + 2),
               0);
        v530 = nn;
        if ( !nn )
        {
LABEL_1332:
          *(_DWORD *)(v2 + 44) |= 1u;
          goto LABEL_129;
        }
        v531 = *(_QWORD *)(nn + 24);
        v532 = *(_QWORD *)(v531 + 16);
        if ( v532 == v530 )
        {
          *(_QWORD *)(v531 + 16) = *(_QWORD *)(v530 + 40);
          goto LABEL_1341;
        }
        if ( !v532 )
          goto LABEL_1341;
        while ( 1 )
        {
          v533 = (_QWORD *)(v532 + 40);
          v532 = *(_QWORD *)(v532 + 40);
          if ( v532 == v530 )
            break;
          if ( !v532 )
            goto LABEL_1341;
        }
        *v533 = *(_QWORD *)(v530 + 40);
LABEL_1341:
        nn = sqlite3FreeIndex(v2, v530);
        *(_DWORD *)(v2 + 44) |= 1u;
        goto LABEL_129;
      case 153:
        v33 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v33 + 20) & 0x9000) != 0 )
        {
          v36 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v33);
          v7 = Table;
          v33 = v36;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        *(_WORD *)(v33 + 20) = 8;
LABEL_28:
        nn = *((_QWORD *)v17 + 2);
        v35 = *(_QWORD *)nn;
        goto LABEL_29;
      case 154:
        nn = sqlite3HashInsert(
               *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 24) + 56LL,
               *((_QWORD *)v17 + 2),
               0);
        v534 = nn;
        if ( !nn )
          goto LABEL_129;
        v535 = *(_QWORD *)(nn + 48);
        if ( *(_QWORD *)(nn + 40) != v535 )
          goto LABEL_1350;
        v536 = *(_QWORD *)(findElementWithHash(v535 + 8, *(_QWORD *)(nn + 8), 0) + 16);
        if ( !v536 )
          goto LABEL_1350;
        v537 = *(_QWORD *)(v536 + 88);
        v538 = (_QWORD *)(v536 + 88);
        if ( !v537 )
          goto LABEL_1350;
        while ( v537 != v534 )
        {
          v538 = (_QWORD *)(v537 + 64);
          v537 = *(_QWORD *)(v537 + 64);
          if ( !v537 )
            goto LABEL_1350;
        }
        *v538 = *(_QWORD *)(v537 + 64);
LABEL_1350:
        nn = sqlite3DeleteTrigger(v2, v534);
        *(_DWORD *)(v2 + 44) |= 1u;
        goto LABEL_129;
      case 155:
        v539 = 56LL * *((int *)v17 + 1);
        v540 = v5 + v539 + 56;
        v543 = sqlite3BtreeIntegrityCheck(
                 v2,
                 *(_QWORD *)(32LL * *((unsigned __int16 *)v17 + 1) + *(_QWORD *)(v2 + 32) + 8),
                 *((_DWORD *)v17 + 4) + 4,
                 (int)v5 + 56 * *((_DWORD *)v17 + 3),
                 *((_DWORD *)v17 + 2),
                 *(_DWORD *)(v539 + v5) + 1,
                 (__int64)&v808,
                 (__int64)&v809);
        Table = v543;
        if ( (*(_WORD *)(v540 + 20) & 0x9000) != 0 )
          vdbeMemClearExternAndSetNull(v540, v541, v8);
        else
          *(_WORD *)(v540 + 20) = 1;
        if ( !v808 )
          goto LABEL_1358;
        if ( v543 )
        {
          sqlite3_free(v809);
          LODWORD(v7) = v543;
          goto LABEL_289;
        }
        v544 = v809;
        LOBYTE(v542) = 1;
        *(_QWORD *)(v539 + v794) -= v808 - 1;
        sqlite3VdbeMemSetStr(v540, v544, -1, v542, sqlite3_free);
LABEL_1358:
        if ( (*(_BYTE *)(v540 + 20) & 2) != 0 )
        {
          if ( *(_BYTE *)(v540 + 22) != v788 )
            sqlite3VdbeMemTranslate(v540, v788);
        }
        else
        {
          *(_BYTE *)(v540 + 22) = v788;
        }
LABEL_1360:
        v14 = v793;
        goto LABEL_1361;
      case 156:
        v548 = v5 + 56LL * *((int *)v17 + 1);
        v549 = (_QWORD *)(v5 + 56LL * *((int *)v17 + 2));
        if ( (*(_BYTE *)(v548 + 20) & 0x10) == 0
          && (unsigned int)sqlite3VdbeMemSetRowSet(v5 + 56LL * *((int *)v17 + 1), 0x180000000uLL, v8) )
        {
          goto LABEL_82;
        }
LABEL_1392:
        nn = sqlite3RowSetInsert(*(_QWORD *)(v548 + 8), *v549, v8);
        goto LABEL_67;
      case 157:
        v571 = *((int *)v17 + 2);
        v572 = v6[13] + 56 * v571;
        if ( (*(_WORD *)(v572 + 20) & 0x9000) != 0 )
        {
          v573 = out2PrereleaseWithClear(v6[13] + 56 * v571, 0x180000000uLL);
          v5 = v794;
          v572 = v573;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(v572 + 20) = 4;
        }
        v574 = v6[33];
        v575 = *((_DWORD *)v17 + 1) + *(_DWORD *)(*(_QWORD *)(v574 + 16) + 24LL * *(int *)(v574 + 76) + 4);
        v576 = *(_QWORD *)(v574 + 24) + 56LL * v575;
        if ( (*(_WORD *)(v572 + 20) & 0x9000) == 0 )
        {
          _XMM0 = *(__m128i *)v576;
          v12 = 0x180000000uLL;
          v8 = v792;
          nn = 0x2000;
          *(_OWORD *)v572 = *(_OWORD *)v576;
          *(_QWORD *)(v572 + 16) = *(_QWORD *)(v576 + 16);
          if ( (*(_WORD *)(v576 + 20) & 0x2000) == 0 )
          {
            *(_WORD *)(v572 + 20) &= 0xCFFFu;
            nn = 0x4000;
            *(_WORD *)(v572 + 20) |= 0x4000u;
          }
          v7 = Table;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v70 = *(_QWORD *)(v574 + 24) + 56LL * v575;
        v71 = v572;
LABEL_128:
        nn = vdbeClrCopy(v71, v70, 0x4000);
        goto LABEL_129;
      case 158:
        if ( (*(_DWORD *)(v2 + 48) & 0x80000) != 0 )
        {
          nn = *((int *)v17 + 2);
          *(_QWORD *)(v2 + 752) += nn;
          v10 = v805;
          v17 += 24;
        }
        else
        {
          nn = *((int *)v17 + 2);
          if ( *((_DWORD *)v17 + 1) )
            *(_QWORD *)(v2 + 744) += nn;
          else
            v6[10] += nn;
          v10 = v805;
          v17 += 24;
        }
        continue;
      case 159:
        v577 = v6[33];
        if ( v577 )
        {
          for ( i4 = *(_QWORD *)(v577 + 8); i4; i4 = *(_QWORD *)(i4 + 8) )
            v577 = i4;
          v579 = (__int64 *)(*(_QWORD *)(v577 + 24) + 56LL * *((int *)v17 + 1));
        }
        else
        {
          v579 = (__int64 *)(v5 + 56LL * *((int *)v17 + 1));
        }
        sqlite3VdbeMemIntegerify(v579);
        v580 = (__int64 *)(v794 + 56LL * *((int *)v17 + 2));
        sqlite3VdbeMemIntegerify(v580);
        nn = *v580;
        v7 = Table;
        v9 = v788;
        if ( *v579 < *v580 )
          *v579 = nn;
        goto LABEL_163;
      case 160:
        v582 = (__int64 *)(v5 + 56LL * *((int *)v17 + 1));
        v583 = (__int64 *)(v5 + 56LL * *((int *)v17 + 3));
        v584 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v584 + 20) & 0x9000) != 0 )
        {
          v585 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v584);
          v7 = Table;
          v584 = v585;
          v5 = v794;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(v584 + 20) = 4;
        }
        v586 = *v582;
        if ( *v582 <= 0 )
          goto LABEL_1449;
        v587 = *v583;
        if ( *v583 <= 0 )
          v587 = 0;
        if ( v587 >= 0 && 0x7FFFFFFFFFFFFFFFLL - v586 < v587 )
        {
LABEL_1449:
          nn = -1;
          *(_QWORD *)v584 = -1;
        }
        else
        {
          nn = v587 + v586;
          *(_QWORD *)v584 = v587 + v586;
        }
        goto LABEL_164;
      case 161:
      case 162:
        v590 = *((unsigned __int16 *)v17 + 1);
        v591 = sqlite3DbMallocRawNN(v2, 8 * v590 + 104);
        if ( !v591 )
        {
LABEL_1928:
          v11 = v795;
          v4 = (unsigned __int8 *)v793;
          goto LABEL_83;
        }
        v592 = v17;
        v5 = v794;
        *(_QWORD *)(v591 + 16) = 0;
        *(_QWORD *)v591 = v591 + 8 * (v590 + 6);
        *(_WORD *)(v591 + 8 * v590 + 68) = 1;
        *(_QWORD *)(v591 + 8 * v590 + 72) = v2;
        *(_DWORD *)(v591 + 8 * v590 + 80) = 0;
        *(_QWORD *)(v591 + 8) = *((_QWORD *)v17 + 2);
        *(_DWORD *)(v591 + 32) = (__int64)&v17[-v14] / 24;
        *(_QWORD *)(v591 + 24) = v6;
        *(_BYTE *)(v591 + 41) = 0;
        *(_DWORD *)(v591 + 36) = 0;
        *(_BYTE *)(v591 + 40) = v788;
        *(_BYTE *)(v591 + 42) = v590;
        v17[1] = -15;
        *((_QWORD *)v17 + 2) = v591;
        *v17 = -93;
LABEL_1460:
        v593 = (__int64 *)*((_QWORD *)v592 + 2);
        v594 = v5 + 56LL * *((int *)v592 + 3);
        if ( v593[2] != v594 )
        {
          v593[2] = v594;
          v595 = *((unsigned __int8 *)v593 + 42) - 1LL;
          v596 = *((unsigned __int8 *)v593 + 42) - 1;
          if ( v595 >= 0 )
          {
            v597 = &v593[v595 + 6];
            do
            {
              --v597;
              v598 = v596 + *((_DWORD *)v17 + 2);
              --v596;
              --v595;
              v597[1] = v5 + 56LL * v598;
            }
            while ( v595 >= 0 );
            v2 = v796;
          }
          v592 = v17;
        }
        ++*(_DWORD *)(v594 + 16);
        v599 = v593 + 6;
        v600 = v593[1];
        v601 = *((unsigned __int8 *)v593 + 42);
        if ( *((_DWORD *)v592 + 1) )
          (*(void (__fastcall **)(__int64 *, __int64, __int64 *))(v600 + 48))(v593, v601, v599);
        else
          (*(void (__fastcall **)(__int64 *, __int64, __int64 *))(v600 + 24))(v593, v601, v599);
        nn = *((unsigned int *)v593 + 9);
        if ( (_DWORD)nn )
        {
          if ( (int)nn > 0 )
          {
            v603 = *v593;
            if ( *v593 )
            {
              v605 = *(unsigned __int16 *)(v603 + 20);
              if ( (v605 & 0x202) == 0x202 && *(_BYTE *)(v603 + 22) == 1 )
              {
                v604 = *(const char **)(v603 + 8);
              }
              else if ( (v605 & 1) != 0 )
              {
                v604 = 0;
              }
              else
              {
                LOBYTE(v605) = 1;
                v604 = (const char *)valueToText(v603, v605);
              }
            }
            else
            {
              v604 = 0;
            }
            sqlite3VdbeError(v6, "%s", v604);
            Table = *((_DWORD *)v593 + 9);
            v3 = 0;
          }
          if ( *((_BYTE *)v593 + 41) )
          {
            v606 = *((int *)v17 - 5);
            if ( (_DWORD)v606 )
            {
              v607 = v794 + 56 * v606;
              if ( (*(_WORD *)(v607 + 20) & 0x9000) != 0 )
              {
                vdbeReleaseAndSetInt64(v607, 1, v8, v602);
              }
              else
              {
                *(_QWORD *)v607 = 1;
                *(_WORD *)(v607 + 20) = 4;
              }
            }
            *((_BYTE *)v593 + 41) = 0;
          }
          v608 = *v593;
          if ( (*(_WORD *)(*v593 + 20) & 0x9000) != 0 || *(_DWORD *)(v608 + 32) )
            vdbeMemClear(v608);
          nn = *v593;
          v7 = Table;
          *(_WORD *)(*v593 + 20) = 1;
          *((_DWORD *)v593 + 9) = 0;
          if ( Table )
            goto LABEL_289;
          v5 = v794;
          v9 = v788;
          goto LABEL_165;
        }
LABEL_1783:
        v7 = Table;
        v9 = v788;
        goto LABEL_162;
      case 163:
        v592 = v17;
        goto LABEL_1460;
      case 164:
      case 165:
        *((_QWORD *)&v609 + 1) = *((_QWORD *)v17 + 2);
        v610 = *((int *)v17 + 3);
        v611 = v5 + 56LL * *((int *)v17 + 1);
        if ( (_DWORD)v610 )
        {
          _XMM0.m128i_i64[0] = 0;
          v855 = 0;
          v856 = 0;
          v858 = 0;
          *(_QWORD *)&v609 = v5 + 56 * v610;
          v857 = 0;
          if ( (*(_WORD *)(v609 + 20) & 0x9000) != 0 )
            vdbeMemClearExternAndSetNull(v609, 0x180000000uLL, v8);
          else
            *(_WORD *)(v609 + 20) = 1;
          v855 = v609;
          *(_QWORD *)&v856 = v611;
          BYTE8(v857) = *(_BYTE *)(*(_QWORD *)(v611 + 24) + 100LL);
          (*(void (__fastcall **)(__int128 *))(*((_QWORD *)&v609 + 1) + 40LL))(&v855);
          v5 = v794;
          v7 = DWORD1(v857);
          v14 = v793;
          nn = *((int *)v17 + 3);
          Table = DWORD1(v857);
          v611 = v794 + 56 * nn;
        }
        else
        {
          nn = sqlite3VdbeMemFinalize(v5 + 56LL * *((int *)v17 + 1), *((_QWORD *)v17 + 2), v8, v7);
          v5 = v794;
          v7 = (unsigned int)nn;
          Table = nn;
        }
        if ( (_DWORD)v7 )
        {
          if ( v611 )
          {
            v773 = *(_WORD *)(v611 + 20);
            v774 = 514;
            if ( (v773 & 0x202) == 0x202 && *(_BYTE *)(v611 + 22) == 1 )
            {
              v3 = *(_QWORD *)(v611 + 8);
            }
            else if ( (v773 & 1) == 0 )
            {
              LOBYTE(v774) = 1;
              v3 = valueToText(v611, v774);
            }
          }
          sqlite3VdbeError(v6, "%s", (const char *)v3);
          LODWORD(v7) = Table;
          goto LABEL_289;
        }
        v9 = v788;
        if ( (*(_BYTE *)(v611 + 20) & 2) == 0 )
        {
          *(_BYTE *)(v611 + 22) = v788;
          goto LABEL_165;
        }
        if ( *(_BYTE *)(v611 + 22) == v788 )
          goto LABEL_162;
        nn = sqlite3VdbeMemTranslate(v611, v788);
        goto LABEL_129;
      case 166:
        if ( *((_DWORD *)v17 + 1) )
        {
          nn = *((unsigned int *)v6 + 50);
          *((_DWORD *)v6 + 50) = nn ^ ((unsigned __int8)nn ^ (unsigned __int8)(*((_DWORD *)v17 + 2) + 1)) & 3;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v641 = *(_QWORD *)(v2 + 8);
        for ( i5 = *((_DWORD *)v17 + 2); v641; v641 = *(_QWORD *)(v641 + 16) )
        {
          nn = *(unsigned int *)(v641 + 200);
          *(_DWORD *)(v641 + 200) = nn ^ ((unsigned __int8)nn ^ (unsigned __int8)(i5 + 1)) & 3;
        }
        goto LABEL_165;
      case 167:
        nn = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL);
        *(_BYTE *)(nn + 1) |= 0x40u;
        v10 = v805;
        v17 += 24;
        continue;
      case 168:
        nn = *(_QWORD *)(*(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1)) + 48LL);
        *(_BYTE *)(nn + 1) &= ~0x40u;
        v10 = v805;
        v17 += 24;
        continue;
      case 170:
        v643 = *(int *)(v2 + 532);
        v644 = *((_QWORD *)v17 + 2);
        Table = 0;
        if ( (int)v643 > 0 && !*(_QWORD *)(v2 + 568) )
        {
          LODWORD(v7) = 6;
          Table = 6;
          v645 = 6;
          if ( !v644 )
            goto LABEL_289;
          goto LABEL_1620;
        }
        if ( !v644 )
        {
          v3 = 0;
          v12 = 0x180000000uLL;
          v7 = 0;
          Table = 0;
          v10 = v805;
          v17 += 24;
          continue;
        }
        v646 = *(__int64 **)(v644 + 16);
        v647 = *v646;
        if ( *(_QWORD *)(*v646 + 112) )
        {
          v648 = 0;
          if ( (int)v643 > 0 )
          {
            v649 = *(_QWORD **)(v2 + 568);
            while ( *v649 != v644 )
            {
              ++v648;
              ++v649;
              if ( v648 >= v643 )
                goto LABEL_1614;
            }
            v645 = 0;
            Table = 0;
LABEL_1620:
            nn = sqlite3VtabImportErrmsg(v6, *(_QWORD *)(v644 + 16));
            v7 = Table;
            if ( v645 )
              goto LABEL_289;
            v5 = v794;
            v3 = 0;
            v9 = v788;
            goto LABEL_164;
          }
LABEL_1614:
          Table = growVTrans(v2);
          LODWORD(v3) = Table;
          if ( !Table )
          {
            Table = (*(__int64 (__fastcall **)(_QWORD))(v647 + 112))(*(_QWORD *)(v644 + 16));
            LODWORD(v3) = Table;
            if ( !Table )
            {
              v650 = *(_DWORD *)(v2 + 736) + *(_DWORD *)(v2 + 740);
              *(_QWORD *)(*(_QWORD *)(v2 + 568) + 8LL * (int)(*(_DWORD *)(v2 + 532))++) = v644;
              ++*(_DWORD *)(v644 + 24);
              if ( v650 )
              {
                if ( *(_QWORD *)(v647 + 160) )
                {
                  *(_DWORD *)(v644 + 32) = v650;
                  LODWORD(v3) = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(v647 + 160))(
                                  *(_QWORD *)(v644 + 16),
                                  (unsigned int)(v650 - 1));
                  Table = v3;
                }
              }
            }
          }
        }
        v645 = v3;
        goto LABEL_1620;
      case 171:
        _XMM0.m128i_i64[0] = 0;
        v829 = 0;
        v833 = 0;
        v830 = 0;
        v831 = v2;
        v832 = 0;
        v651 = sqlite3VdbeMemCopy(&v829, v5 + 56LL * *((int *)v17 + 2), v8, v7);
        v652 = WORD6(v830);
        v653 = 514;
        Table = v651;
        if ( (WORD6(v830) & 0x202) == 0x202 && BYTE14(v830) == 1 )
        {
          v654 = v830;
        }
        else
        {
          if ( (BYTE12(v830) & 1) != 0 )
            goto LABEL_1644;
          LOBYTE(v653) = 1;
          v654 = valueToText(&v829, v653);
          v652 = WORD6(v830);
        }
        if ( !v654 )
          goto LABEL_1644;
        v655 = sqlite3FindTable(v2, v654, *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32)));
        v656 = **(const char ***)(v655 + 72);
        v657 = *(_QWORD *)(findElementWithHash(v2 + 536, v656, 0) + 16);
        if ( v657 && (v658 = *(_QWORD *)(*(_QWORD *)v657 + 8LL)) != 0 && *(_QWORD *)(*(_QWORD *)v657 + 40LL) )
        {
          Table = vtabCallConstructor(v2, v655, v657, v658, (__int64)(v6 + 21));
          if ( !Table )
          {
            v659 = *(_QWORD **)(v655 + 80);
            if ( v659 )
            {
              while ( *v659 != v2 )
              {
                v659 = (_QWORD *)v659[5];
                if ( !v659 )
                {
                  v652 = WORD6(v830);
                  v14 = v793;
                  goto LABEL_1644;
                }
              }
              Table = growVTrans(v2);
              if ( !Table )
              {
                for ( i6 = *(_QWORD *)(v655 + 80); i6; i6 = *(_QWORD *)(i6 + 40) )
                {
                  if ( *(_QWORD *)i6 == v2 )
                    break;
                }
                v14 = v793;
                *(_QWORD *)(*(_QWORD *)(v2 + 568) + 8LL * (int)(*(_DWORD *)(v2 + 532))++) = i6;
                ++*(_DWORD *)(i6 + 24);
                v652 = WORD6(v830);
LABEL_1644:
                nn = 36864;
                if ( (v652 & 0x9000) != 0 || (_DWORD)v832 )
                  nn = vdbeMemClear(&v829);
                v7 = Table;
                if ( Table )
                  goto LABEL_289;
                v5 = v794;
                v3 = 0;
                v9 = v788;
                goto LABEL_165;
              }
            }
          }
        }
        else
        {
          v6[21] = sqlite3MPrintf(v2, "no such module: %s", v656);
          Table = 1;
        }
        v652 = WORD6(v830);
        v14 = v793;
        goto LABEL_1644;
      case 172:
        ++*(_DWORD *)(v2 + 232);
        nn = sqlite3VtabCallDestroy(v2, *((unsigned int *)v17 + 1), *((_QWORD *)v17 + 2), v7);
        --*(_DWORD *)(v2 + 232);
        v7 = (unsigned int)nn;
        Table = nn;
        if ( (_DWORD)nn )
          goto LABEL_289;
        v5 = v794;
        v9 = v788;
        goto LABEL_165;
      case 173:
        v816 = 0;
        v661 = *(__int64 **)(*((_QWORD *)v17 + 2) + 16LL);
        if ( !v661 || (v662 = *v661) == 0 )
        {
LABEL_1889:
          LODWORD(v7) = 6;
          goto LABEL_288;
        }
        Table = (*(__int64 (__fastcall **)(__int64 *, __int64 ***, __int64, __int64))(v662 + 48))(v661, &v816, v8, v7);
        sqlite3VtabImportErrmsg(v6, v661);
        v7 = Table;
        if ( Table )
          goto LABEL_289;
        LOBYTE(v7) = 2;
        *v816 = v661;
        nn = allocateCursor(v6, *((unsigned int *)v17 + 1), 0, v7);
        if ( !nn )
        {
          (*(void (__fastcall **)(__int64 **))(v662 + 56))(v816);
          goto LABEL_82;
        }
        *(_QWORD *)(nn + 48) = v816;
        ++*((_DWORD *)v661 + 2);
        v3 = 0;
        goto LABEL_67;
      case 174:
        v663 = v17;
        v818 = 0;
        nn = 36864;
        v664 = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v664 + 20) & 0x9000) != 0 )
        {
          nn = vdbeMemClearExternAndSetNull(v5 + 56LL * *((int *)v17 + 2), 0x180000000uLL, v8);
          v663 = v17;
          v5 = v794;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(v664 + 20) = 1;
        }
        v665 = (_QWORD *)*((_QWORD *)v663 + 2);
        v666 = v665[10];
        if ( !v666 )
          goto LABEL_1663;
        v667 = *(__int64 **)(v666 + 16);
        v668 = *v667;
        ++*(_DWORD *)(v666 + 24);
        Table = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64 *))(v668 + 192))(
                  v667,
                  *(_QWORD *)(32LL * *((int *)v663 + 1) + *(_QWORD *)(v2 + 32)),
                  *v665,
                  *((unsigned int *)v663 + 3),
                  &v818);
        nn = sqlite3VtabUnlock(v665[10]);
        v7 = Table;
        if ( Table )
        {
          v776 = v818;
          if ( v818 )
          {
            if ( dword_1803379C0 )
            {
              if ( (_QWORD)xmmword_1803DC8D0 )
                xmmword_180337A40(xmmword_1803DC8D0);
              v777 = (*((__int64 (__fastcall **)(__int64))&xmmword_1803379F0 + 1))(v776);
              --qword_1803DC858;
              qword_1803DC810 -= v777;
              (*((void (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(v776);
              if ( (_QWORD)xmmword_1803DC8D0 )
                xmmword_180337A50(xmmword_1803DC8D0);
              LODWORD(v7) = Table;
            }
            else
            {
              (*((void (__fastcall **)(__int64))&xmmword_1803379E0 + 1))(v818);
              LODWORD(v7) = Table;
            }
          }
          goto LABEL_289;
        }
        if ( !v818 )
          goto LABEL_1785;
        LOBYTE(v7) = 1;
        nn = sqlite3VdbeMemSetStr(v664, v818, -1, v7, sqlite3_free);
        v3 = 0;
        goto LABEL_67;
      case 175:
        v669 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v670 = (_QWORD *)sqlite3Malloc(16);
        v671 = v670;
        if ( !v670 )
          goto LABEL_82;
        *v670 = *(_QWORD *)(v669 + 48);
        v672 = v794 + 56LL * *((int *)v17 + 3);
        v670[1] = v672;
        v673 = *((int *)v17 + 2);
        v674 = v6[13] + 56 * v673;
        if ( (*(_WORD *)(v674 + 20) & 0x9000) != 0 )
          v674 = out2PrereleaseWithClear(v6[13] + 56 * v673, v672);
        *(_WORD *)(v674 + 20) = 1;
        vdbeMemClear(v674);
        *(_QWORD *)v674 = "ValueList";
        nn = (__int64)sqlite3VdbeValueListFree;
        *(_QWORD *)(v674 + 8) = v671;
        *(_WORD *)(v674 + 20) = 6657;
        *(_BYTE *)(v674 + 23) = 112;
        *(_QWORD *)(v674 + 48) = sqlite3VdbeValueListFree;
        goto LABEL_67;
      case 176:
        v702 = *(_QWORD *)(v6[15] + 8LL * *((int *)v17 + 1));
        v703 = v5 + 56LL * *((int *)v17 + 3);
        if ( !*(_BYTE *)(v702 + 2) )
        {
          _XMM0.m128i_i64[0] = 0;
          v704 = v17;
          v705 = **(__int64 ***)(v702 + 48);
          v706 = *v705;
          v862 = 0;
          v861 = 0;
          v859[1] = &v872;
          v860 = 0;
          v859[0] = v703;
          BYTE8(v861) = v9;
          v874 = 0;
          v873 = 0x1000000;
          if ( (v17[2] & 1) != 0 )
          {
            if ( (*(_WORD *)(v703 + 20) & 0x9000) != 0 )
            {
              vdbeMemClearExternAndSetNull(v703, 0x180000000uLL, v8);
              v704 = v17;
            }
            *(_WORD *)(v703 + 20) = 1025;
            *(_DWORD *)v703 = 0;
          }
          else
          {
            *(_WORD *)(v703 + 20) &= 0xF241u;
            *(_WORD *)(v703 + 20) |= 1u;
          }
          Table = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, __int64))(v706 + 88))(
                    *(_QWORD *)(v702 + 48),
                    v859,
                    *((unsigned int *)v704 + 2),
                    v7);
          nn = sqlite3VtabImportErrmsg(v6, v705);
          if ( SDWORD1(v861) > 0 )
          {
            if ( v703 )
            {
              v708 = *(_WORD *)(v703 + 20);
              v709 = 514;
              if ( (v708 & 0x202) == 0x202 && *(_BYTE *)(v703 + 22) == 1 )
              {
                v707 = *(const char **)(v703 + 8);
              }
              else if ( (v708 & 1) != 0 )
              {
                v707 = 0;
              }
              else
              {
                LOBYTE(v709) = 1;
                v707 = (const char *)valueToText(v703, v709);
              }
            }
            else
            {
              v707 = 0;
            }
            nn = sqlite3VdbeError(v6, "%s", v707);
            Table = DWORD1(v861);
          }
          v9 = v788;
          if ( (*(_BYTE *)(v703 + 20) & 2) != 0 )
          {
            if ( *(_BYTE *)(v703 + 22) != v788 )
            {
              nn = sqlite3VdbeMemTranslate(v703, v788);
              v9 = v788;
            }
          }
          else
          {
            *(_BYTE *)(v703 + 22) = v788;
          }
          goto LABEL_1575;
        }
        nn = 36864;
        if ( (*(_WORD *)(v703 + 20) & 0x9000) != 0 )
        {
          nn = vdbeMemClearExternAndSetNull(v703, 0x180000000uLL, v8);
          goto LABEL_67;
        }
        v14 = v793;
        *(_WORD *)(v703 + 20) = 1;
        v10 = v805;
        v17 += 24;
        continue;
      case 177:
        v714 = *(_DWORD *)(v2 + 48);
        *(_QWORD *)(v2 + 48) |= 0x4000000uLL;
        v715 = v714 & 0x4000000;
        v716 = *(_QWORD *)(*((_QWORD *)v17 + 2) + 16LL);
        v717 = *((int *)v17 + 1);
        v718 = v5 + 56 * v717;
        if ( (*(_BYTE *)(v718 + 20) & 2) != 0 )
        {
          if ( *(_BYTE *)(v718 + 22) != 1 )
          {
            LOBYTE(v12) = 1;
            Table = sqlite3VdbeMemTranslate(v5 + 56 * v717, v12);
            v7 = Table;
            if ( Table )
              goto LABEL_289;
          }
        }
        else
        {
          *(_BYTE *)(v718 + 22) = 1;
        }
        Table = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v716 + 152LL))(
                  v716,
                  *(_QWORD *)(v718 + 8),
                  *(_QWORD *)(*(_QWORD *)v716 + 152LL),
                  v7);
        if ( !v715 )
          *(_QWORD *)(v2 + 48) &= ~0x4000000uLL;
        nn = sqlite3VtabImportErrmsg(v6, v716);
        *((_DWORD *)v6 + 50) &= 0xFFFFFFFC;
        v7 = Table;
        if ( Table )
          goto LABEL_289;
        v3 = 0;
        v5 = v794;
        v9 = v788;
        goto LABEL_164;
      case 178:
        v33 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v33 + 20) & 0x9000) != 0 )
        {
          v727 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), v33);
          v7 = Table;
          v33 = v727;
          v5 = v794;
          v9 = v788;
          v8 = v792;
        }
        else
        {
          *(_WORD *)(v33 + 20) = 4;
        }
        nn = *(_QWORD *)(*(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 8) + 8LL);
        v35 = *(unsigned int *)(nn + 64);
LABEL_29:
        *(_QWORD *)v33 = v35;
        goto LABEL_30;
      case 179:
        v728 = v6[13] + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v728 + 20) & 0x9000) != 0 )
        {
          v729 = out2PrereleaseWithClear(v6[13] + 56LL * *((int *)v17 + 2), 0x180000000uLL);
          v5 = v794;
          v728 = v729;
          v9 = v788;
        }
        else
        {
          *(_WORD *)(v728 + 20) = 4;
        }
        v730 = 0;
        v731 = *(_QWORD *)(32LL * *((int *)v17 + 1) + *(_QWORD *)(v2 + 32) + 8);
        v732 = *((_DWORD *)v17 + 3);
        if ( v732 )
        {
          v730 = *(_DWORD *)(*(_QWORD *)(v731 + 8) + 64LL);
          if ( v730 < v732 )
            v730 = *((_DWORD *)v17 + 3);
        }
        v733 = **(_QWORD **)(v731 + 8);
        if ( v730 )
          *(_DWORD *)(v733 + 188) = v730;
        nn = *(unsigned int *)(v733 + 188);
        v7 = Table;
        *(_QWORD *)v728 = nn;
        goto LABEL_165;
      case 180:
        nn = 63487;
        *(_WORD *)(56LL * *((int *)v17 + 1) + v5 + 20) &= ~0x800u;
        v10 = v805;
        v17 += 24;
        continue;
      case 181:
        v750 = 56LL * *((int *)v17 + 1);
        v751 = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_WORD *)(v750 + v5 + 20) & 0x800) != 0 )
        {
          nn = *(unsigned __int8 *)(v750 + v5 + 23);
          if ( (*(_WORD *)(v751 + 20) & 0x9000) != 0 )
          {
            nn = vdbeReleaseAndSetInt64(v751, *(unsigned __int8 *)(v750 + v5 + 23), v8, v7);
            goto LABEL_129;
          }
          *(_QWORD *)v751 = nn;
          *(_WORD *)(v751 + 20) = 4;
        }
        else
        {
          nn = 36864;
          if ( (*(_WORD *)(v751 + 20) & 0x9000) != 0 )
          {
            nn = vdbeMemClearExternAndSetNull(v751, v750, v8);
            goto LABEL_129;
          }
          *(_WORD *)(v751 + 20) = 1;
        }
LABEL_30:
        v12 = 0x180000000uLL;
        v10 = v805;
        v17 += 24;
        continue;
      case 182:
        v752 = 56LL * *((int *)v17 + 1);
        v753 = v5 + 56LL * *((int *)v17 + 2);
        if ( (*(_BYTE *)(v752 + v5 + 20) & 1) != 0 )
        {
          nn = 63487;
          v12 = 0x180000000uLL;
          *(_WORD *)(v753 + 20) &= ~0x800u;
        }
        else
        {
          *(_WORD *)(v753 + 20) |= 0x800u;
          nn = *(unsigned __int8 *)(v752 + v5);
          v12 = 0x180000000uLL;
          *(_BYTE *)(v753 + 23) = nn;
        }
        v10 = v805;
        v17 += 24;
        continue;
      case 183:
        v754 = 56LL * *((int *)v17 + 1);
        v755 = filterHash(v5, v17, v8, v7);
        v5 = v794;
        v7 = Table;
        v9 = v788;
        v756 = *(_QWORD *)(v754 + v794 + 8);
        v757 = (v755 % (8 * *(_DWORD *)(v754 + v794 + 16))) & 7;
        v758 = (v755 % (8 * *(_DWORD *)(v754 + v794 + 16))) >> 3;
        nn = (unsigned int)*(char *)(v758 + v756);
        LODWORD(nn) = nn | (1 << v757);
        *(_BYTE *)(v758 + v756) = nn;
        goto LABEL_165;
      default:
        nn = v20;
        goto LABEL_167;
    }
  }
}

```

## disassembly

```asm
0x180138880  mov     [rsp-8+arg_10], rsi
0x180138885  mov     [rsp-8+arg_18], rdi
0x18013888a  push    rbp
0x18013888b  push    r12
0x18013888d  push    r13
0x18013888f  push    r14
0x180138891  push    r15
0x180138893  lea     rbp, [rsp-3B0h]
0x18013889b  sub     rsp, 4B0h
0x1801388a2  mov     rax, cs:__security_cookie
0x1801388a9  xor     rax, rsp
0x1801388ac  mov     [rbp+3D0h+var_80], rax
0x1801388b3  mov     r14, [rcx]
0x1801388b6  xor     r12d, r12d
0x1801388b9  mov     r15, [rcx+88h]
0x1801388c0  xor     sil, sil
0x1801388c3  mov     r11, [rcx+68h]
0x1801388c7  mov     r13, rcx
0x1801388ca  mov     [rbp+3D0h+var_448], sil
0x1801388ce  mov     r9d, r12d
0x1801388d1  mov     r8d, r12d
0x1801388d4  movzx   r10d, byte ptr [r14+64h]
0x1801388d9  mov     esi, r12d
0x1801388dc  mov     [rsp+4D0h+var_490], r10b
0x1801388e1  mov     [rsp+4D0h+var_458], rcx
0x1801388e6  mov     [rsp+4D0h+var_478], r15
0x1801388eb  mov     [rsp+4D0h+var_488], r15
0x1801388f0  mov     [rsp+4D0h+var_48C], r12d
0x1801388f5  mov     [rsp+4D0h+var_460], r14
0x1801388fa  mov     [rsp+4D0h+var_480], r12d
0x1801388ff  mov     [rbp+3D0h+var_420], r12
0x180138903  mov     [rsp+4D0h+var_470], r11
0x180138908  mov     [rbp+3D0h+var_438], r12d
0x18013890c  cmp     [r14+200h], r12
0x180138913  jz      short loc_18013892D
0x180138915  mov     ecx, [r14+210h]
0x18013891c  xor     edx, edx
0x18013891e  mov     eax, [r13+0E4h]
0x180138925  div     ecx
0x180138927  sub     ecx, edx
0x180138929  mov     edi, ecx
0x18013892b  jmp     short loc_180138934
0x18013892d  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180138934  cmp     dword ptr [r13+34h], 7
0x180138939  lea     rdx, cs:180000000h
0x180138940  mov     [rsp+4D0h+arg_8], rbx
0x180138948  movaps  [rsp+4D0h+var_30], xmm6
0x180138950  movaps  [rsp+4D0h+var_40], xmm7
0x180138958  movaps  [rsp+4D0h+var_50], xmm8
0x180138961  movaps  [rsp+4D0h+var_60], xmm9
0x18013896a  movaps  [rsp+4D0h+var_70], xmm10
0x180138973  mov     [rsp+4D0h+var_468], rdi
0x180138978  jz      loc_180139044
0x18013897e  mov     [r13+34h], r12d
0x180138982  mov     [r13+48h], r12
0x180138986  mov     [r14+288h], r12d
0x18013898d  mov     eax, [r14+188h]
0x180138994  test    eax, eax
0x180138996  jnz     loc_18014136D
0x18013899c  movsxd  rax, dword ptr [r13+30h]
0x1801389a0  mov     rdi, r15
0x1801389a3  movdqa  xmm8, cs:__xmm@00000001000000010000000100000001
0x1801389ac  xorps   xmm10, xmm10
0x1801389b0  movdqa  xmm7, cs:__xmm@00000000000000380000000000000038
0x1801389b8  movdqa  xmm9, cs:__xmm@00000003000000020000000100000000
0x1801389c1  lea     rcx, [rax+rax*2]
0x1801389c5  lea     r15, [r15+rcx*8]
0x1801389c9  movzx   ebx, byte ptr [r15]
0x1801389cd  inc     rsi
0x1801389d0  mov     [rsp+4D0h+var_488], r15
0x1801389d5  mov     [rbp+3D0h+var_420], rsi
0x1801389d9  cmp     ebx, 0B8h; switch 185 cases
0x1801389df  ja      def_1801389F2; jumptable 00000001801389F2 default case, cases 89,93,123,169
0x1801389e5  movsxd  rax, ebx
0x1801389e8  mov     ecx, ds:(jpt_1801389F2 - 180000000h)[rdx+rax*4]
0x1801389ef  add     rcx, rdx
0x1801389f2  jmp     rcx; switch jump
0x1801389f4  mov     rcx, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 10
0x1801389f9  movsxd  rax, dword ptr [rcx+4]
0x1801389fd  sub     rcx, rdi
0x180138a00  imul    r8, rax, 38h ; '8'
0x180138a04  mov     rax, 2AAAAAAAAAAAAAABh
0x180138a0e  imul    rcx
0x180138a11  mov     word ptr [r8+r11+14h], 4
0x180138a19  sar     rdx, 2
0x180138a1d  mov     rax, rdx
0x180138a20  shr     rax, 3Fh
0x180138a24  add     rax, rdx
0x180138a27  cdqe
0x180138a29  mov     [r8+r11], rax
0x180138a2d  jmp     loc_1801401F9; jumptable 00000001801389F2 case 9
0x180138a32  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 67
0x180138a37  movsxd  rax, dword ptr [rax+4]
0x180138a3b  imul    rax, 38h ; '8'
0x180138a3f  test    byte ptr [rax+r11+14h], 4
0x180138a45  jz      loc_180138FAE
0x180138a4b  mov     rax, [rax+r11]
0x180138a4f  lea     rcx, [rax+rax*2]
0x180138a53  lea     r15, [rdi+rcx*8]
0x180138a57  mov     rsi, [rbp+3D0h+var_420]
0x180138a5b  add     r15, 18h
0x180138a5f  jmp     loc_1801389C9
0x180138a64  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 11
0x180138a69  mov     r15, [rsp+4D0h+var_488]
0x180138a6e  movsxd  rax, dword ptr [rax+4]
0x180138a72  imul    rcx, rax, 38h ; '8'
0x180138a76  mov     rax, [rsp+4D0h+var_488]
0x180138a7b  mov     eax, [rax+0Ch]
0x180138a7e  dec     eax
0x180138a80  cdqe
0x180138a82  mov     [rcx+r11], rax
0x180138a86  mov     word ptr [rcx+r11+14h], 4
0x180138a8e  cmp     dword ptr [r15+8], 0
0x180138a93  jnz     loc_18013A585
0x180138a99  mov     rsi, [rbp+3D0h+var_420]
0x180138a9d  add     r15, 18h
0x180138aa1  jmp     loc_1801389C9
0x180138aa6  mov     rbx, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 68
0x180138aab  movsxd  rax, dword ptr [rbx+4]
0x180138aaf  sub     rbx, [r13+88h]
0x180138ab6  imul    r8, rax, 38h ; '8'
0x180138aba  mov     rax, [r8+r11]
0x180138abe  lea     rcx, [rax+rax*2]
0x180138ac2  mov     rax, 2AAAAAAAAAAAAAABh
0x180138acc  imul    rbx
0x180138acf  sar     rdx, 2
0x180138ad3  mov     rax, rdx
0x180138ad6  shr     rax, 3Fh
0x180138ada  add     rax, rdx
0x180138add  dec     eax
0x180138adf  cdqe
0x180138ae1  mov     [r8+r11], rax
0x180138ae5  mov     eax, [rdi+rcx*8+8]
0x180138ae9  dec     eax
0x180138aeb  cdqe
0x180138aed  lea     rcx, [rax+rax*2]
0x180138af1  lea     r15, [rdi+rcx*8]
0x180138af5  jmp     loc_1801395D4
0x180138afa  mov     rbx, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 12
0x180138aff  movsxd  rax, dword ptr [rbx+4]
0x180138b03  sub     rbx, rdi
0x180138b06  imul    r8, rax, 38h ; '8'
0x180138b0a  mov     rax, 2AAAAAAAAAAAAAABh
0x180138b14  imul    rbx
0x180138b17  mov     word ptr [r8+r11+14h], 4
0x180138b1f  movsxd  rcx, dword ptr [r8+r11]
0x180138b23  sar     rdx, 2
0x180138b27  mov     rax, rdx
0x180138b2a  shr     rax, 3Fh
0x180138b2e  add     rax, rdx
0x180138b31  lea     rcx, [rcx+rcx*2]
0x180138b35  cdqe
0x180138b37  lea     r15, [rdi+rcx*8]
0x180138b3b  mov     [r8+r11], rax
0x180138b3f  jmp     loc_1801395D4
0x180138b44  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 69
0x180138b49  movsxd  rax, dword ptr [rax+0Ch]
0x180138b4d  imul    rcx, rax, 38h ; '8'
0x180138b51  test    byte ptr [rcx+r11+14h], 1
0x180138b57  jz      loc_180138FAE
0x180138b5d  mov     rcx, [r13+108h]; jumptable 00000001801389F2 case 70
0x180138b64  mov     r9, [rsp+4D0h+var_488]
0x180138b69  test    rcx, rcx
0x180138b6c  jz      loc_180140ACF
0x180138b72  cmp     dword ptr [r9+4], 0
0x180138b77  jnz     loc_180140ACF
0x180138b7d  mov     rax, [rcx+8]
0x180138b81  mov     [r13+108h], rax
0x180138b88  dec     dword ptr [r13+118h]
0x180138b8f  mov     rax, [r13+38h]
0x180138b93  mov     [r14+78h], rax
0x180138b97  add     [r14+80h], rax
0x180138b9e  call    sqlite3VdbeFrameRestore
0x180138ba3  mov     r15, [rsp+4D0h+var_488]
0x180138ba8  cmp     dword ptr [r15+8], 4
0x180138bad  jnz     short loc_180138BC2
0x180138baf  cdqe
0x180138bb1  lea     rcx, [rax+rax*2]
0x180138bb5  mov     rax, [r13+88h]
0x180138bbc  mov     eax, [rax+rcx*8+8]
0x180138bc0  dec     eax
0x180138bc2  mov     rdi, [r13+88h]
0x180138bc9  mov     r11, [r13+68h]
0x180138bcd  movzx   r10d, [rsp+4D0h+var_490]
0x180138bd3  cdqe
0x180138bd5  mov     [rsp+4D0h+var_478], rdi
0x180138bda  mov     [rsp+4D0h+var_470], r11
0x180138bdf  lea     rcx, [rax+rax*2]
0x180138be3  lea     r9, [rdi+rcx*8]
0x180138be7  mov     [rsp+4D0h+var_488], r9
0x180138bec  mov     r15, [rsp+4D0h+var_488]
0x180138bf1  mov     r9d, [rsp+4D0h+var_48C]
0x180138bf6  jmp     loc_1801395D4
0x180138bfb  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 71
0x180138c00  mov     esi, 9000h
0x180138c05  movsxd  rax, dword ptr [rax+8]
0x180138c09  imul    rdx, rax, 38h ; '8'
0x180138c0d  add     rdx, [r13+68h]
0x180138c11  test    [rdx+14h], si
0x180138c15  jz      short loc_180138C5C
0x180138c17  mov     rcx, rdx
0x180138c1a  call    out2PrereleaseWithClear
0x180138c1f  mov     r9d, [rsp+4D0h+var_48C]
0x180138c24  mov     rdx, rax
0x180138c27  mov     rax, [rsp+4D0h+var_488]
0x180138c2c  mov     r11, [rsp+4D0h+var_470]
0x180138c31  movzx   r10d, [rsp+4D0h+var_490]
0x180138c37  mov     r8d, [rsp+4D0h+var_480]
0x180138c3c  movsxd  rax, dword ptr [rax+4]
0x180138c40  mov     r15, [rsp+4D0h+var_488]
0x180138c45  mov     [rdx], rax
0x180138c48  lea     rdx, cs:180000000h
0x180138c4f  mov     rsi, [rbp+3D0h+var_420]
0x180138c53  add     r15, 18h
0x180138c57  jmp     loc_1801389C9
0x180138c5c  mov     rax, [rsp+4D0h+var_488]
0x180138c61  mov     word ptr [rdx+14h], 4
0x180138c67  movsxd  rax, dword ptr [rax+4]
0x180138c6b  mov     [rdx], rax
0x180138c6e  mov     r15, [rsp+4D0h+var_488]
0x180138c73  lea     rdx, cs:180000000h
0x180138c7a  mov     rsi, [rbp+3D0h+var_420]
0x180138c7e  add     r15, 18h
0x180138c82  jmp     loc_1801389C9
0x180138c87  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 72
0x180138c8c  movsxd  rax, dword ptr [rax+8]
0x180138c90  imul    rdx, rax, 38h ; '8'
0x180138c94  mov     eax, 9000h
0x180138c99  add     rdx, [r13+68h]
0x180138c9d  test    [rdx+14h], ax
0x180138ca1  jz      short loc_180138CC5
0x180138ca3  mov     rcx, rdx
0x180138ca6  call    out2PrereleaseWithClear
0x180138cab  mov     r9d, [rsp+4D0h+var_48C]
0x180138cb0  mov     rdx, rax
0x180138cb3  mov     r11, [rsp+4D0h+var_470]
0x180138cb8  movzx   r10d, [rsp+4D0h+var_490]
0x180138cbe  mov     r8d, [rsp+4D0h+var_480]
0x180138cc3  jmp     short loc_180138CCB
0x180138cc5  mov     word ptr [rdx+14h], 4
0x180138ccb  mov     rax, [rsp+4D0h+var_488]
0x180138cd0  mov     rax, [rax+10h]
0x180138cd4  mov     rcx, [rax]
0x180138cd7  mov     [rdx], rcx
0x180138cda  mov     r15, [rsp+4D0h+var_488]
0x180138cdf  lea     rdx, cs:180000000h
0x180138ce6  mov     rsi, [rbp+3D0h+var_420]
0x180138cea  add     r15, 18h
0x180138cee  jmp     loc_1801389C9
0x180138cf3  mov     rax, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 153
0x180138cf8  movsxd  rax, dword ptr [rax+8]
0x180138cfc  imul    rdx, rax, 38h ; '8'
0x180138d00  mov     eax, 9000h
0x180138d05  add     rdx, [r13+68h]
0x180138d09  test    [rdx+14h], ax
0x180138d0d  jz      short loc_180138D2F
0x180138d0f  mov     rcx, rdx
0x180138d12  call    out2PrereleaseWithClear
0x180138d17  mov     r9d, [rsp+4D0h+var_48C]
0x180138d1c  mov     rdx, rax
0x180138d1f  mov     r11, [rsp+4D0h+var_470]
0x180138d24  movzx   r10d, [rsp+4D0h+var_490]
0x180138d2a  mov     r8d, [rsp+4D0h+var_480]
0x180138d2f  mov     word ptr [rdx+14h], 8
0x180138d35  jmp     short loc_180138CCB
0x180138d37  mov     r9, [rsp+4D0h+var_488]; jumptable 00000001801389F2 case 117
0x180138d3c  mov     esi, 9000h
0x180138d41  movsxd  rax, dword ptr [r9+8]
0x180138d45  imul    rbx, rax, 38h ; '8'
0x180138d49  add     rbx, [r13+68h]
0x180138d4d  test    [rbx+14h], si
0x180138d51  jz      short loc_180138D6B
0x180138d53  mov     rcx, rbx
0x180138d56  call    out2PrereleaseWithClear
0x180138d5b  mov     r9, [rsp+4D0h+var_488]
0x180138d60  mov     rbx, rax
0x180138d63  movzx   r10d, [rsp+4D0h+var_490]
0x180138d69  jmp     short loc_180138D71
0x180138d6b  mov     word ptr [rbx+14h], 4
0x180138d71  mov     rdi, [r9+10h]
0x180138d75  test    rdi, rdi
0x180138d78  jnz     short loc_180138D7F
0x180138d7a  mov     eax, r12d
0x180138d7d  jmp     short loc_180138D97
0x180138d7f  mov     rcx, rdi; Str
0x180138d82  call    strlen
0x180138d87  mov     r9, [rsp+4D0h+var_488]
0x180138d8c  and     eax, 3FFFFFFFh
0x180138d91  movzx   r10d, [rsp+4D0h+var_490]
0x180138d97  mov     [r9+4], eax
0x180138d9b  cmp     r10b, 1
0x180138d9f  jz      loc_180138E3F
0x180138da5  mov     r9b, 1
0x180138da8  mov     [rsp+4D0h+var_4B0], r12
0x180138dad  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180138db4  mov     rdx, rdi
0x180138db7  mov     rcx, rbx
0x180138dba  call    sqlite3VdbeMemSetStr
0x180138dbf  mov     [rsp+4D0h+var_48C], eax
0x180138dc3  test    eax, eax
  ... truncated ...
```
