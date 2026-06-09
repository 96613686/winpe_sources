# sqlite3Pragma

- ea: `0x180122820`
- end: `0x180127a0c`
- name: `sqlite3Pragma`
- size: `20972`
- prototype: ``
- caller_count: `1`
- callee_count: `105`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180174050`

## callees

- `0x1800b9810`
- `0x1800b99d0`
- `0x1800bd140`
- `0x1800c6d20`
- `0x1800cf1f0`
- `0x1800d1180`
- `0x1800d51e0`
- `0x1800d8630`
- `0x1800d8770`
- `0x1800da020`
- `0x1800da180`
- `0x1800da1e0`
- `0x1800eac60`
- `0x1800efca0`
- `0x1800efda0`
- `0x1800f4540`
- `0x1800f6760`
- `0x1800f68f0`
- `0x1800f9ce0`
- `0x1800fa020`
- `0x1800fdf90`
- `0x1800ff2c0`
- `0x180102270`
- `0x1801022b0`
- `0x180102310`
- `0x1801023c0`
- `0x180104f10`
- `0x180104fe0`
- `0x1801053f0`
- `0x180107000`
- `0x180108840`
- `0x1801089d0`
- `0x180108a90`
- `0x180108e30`
- `0x18010b290`
- `0x18010ca80`
- `0x18010dd10`
- `0x180110050`
- `0x180110480`
- `0x180111210`
- `0x180111a00`
- `0x180111ad0`
- `0x1801127c0`
- `0x1801128f0`
- `0x1801146f0`
- `0x1801181a0`
- `0x180118ea0`
- `0x180119020`
- `0x18011d320`
- `0x18011d790`

## string_xrefs

- `0x180127087`: `unopened`
- `0x1801278bf`: `unopened`
- `0x180123fd9`: `sqlite_temp_schema`
- `0x1801237af`: `not a writable directory`
- `0x18012390b`: `Safety level may not be changed inside a transaction`

## pseudocode

```c
char *__fastcall sqlite3Pragma(__int64 *a1, __int64 a2, __int64 a3, _QWORD *a4, int a5)
{
  char *v5; // rbx
  __int64 v7; // rax
  __int64 *v10; // r15
  char *result; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // r13
  __int64 v17; // r15
  int v18; // edx
  __int64 v19; // rdi
  int v20; // r13d
  char *v21; // rax
  __int64 v22; // rsi
  int v23; // r8d
  __int64 *v24; // r13
  int v25; // esi
  const char *v26; // rdi
  int v27; // eax
  __int64 v28; // rcx
  _QWORD *v29; // r15
  const char *v30; // rbx
  int v31; // eax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r13
  __int64 *v35; // rsi
  char v36; // al
  char *v37; // r11
  __int64 v38; // rcx
  __int64 v39; // r15
  __int64 v40; // rdi
  __int64 v41; // rdx
  int v42; // r11d
  __int64 v43; // rdi
  unsigned int v44; // r9d
  int v45; // edx
  __int64 v46; // r8
  __int64 v47; // rcx
  char v48; // al
  const char *v49; // rax
  unsigned int v50; // edi
  int v51; // eax
  const char *v52; // r10
  char *v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r8
  unsigned int v56; // r9d
  char *i7; // rdx
  __int64 v58; // r8
  __int64 v59; // rax
  int v60; // eax
  __int64 v61; // rdx
  int v62; // ebx
  __int64 v63; // rcx
  __int64 v64; // rax
  int v65; // eax
  __int64 *v66; // r10
  __int64 v67; // rdi
  unsigned __int8 *v68; // r8
  char *v69; // r9
  int v70; // edx
  __int64 v71; // rcx
  int v72; // ecx
  _QWORD *v73; // rax
  int v74; // edi
  __int64 v75; // r15
  __int64 v76; // r12
  __int64 v77; // rsi
  __int64 *v78; // rcx
  __int64 v79; // rax
  __int64 v80; // rdi
  __int64 v81; // rcx
  __int64 v82; // rdi
  __int64 v83; // rax
  __int64 v84; // rcx
  char *v85; // rdx
  __int64 v86; // rax
  __int64 v87; // r8
  unsigned int v88; // esi
  char *i; // rdx
  __int64 v90; // rax
  __int64 v91; // r8
  char *j; // rdx
  __int64 v93; // rax
  __int64 v94; // r8
  unsigned __int8 v95; // dl
  int v96; // edi
  _DWORD *v97; // rax
  int v98; // edx
  unsigned int v99; // edi
  unsigned int v100; // edi
  int v101; // eax
  int Int32; // eax
  __int64 v103; // r8
  unsigned int v104; // r9d
  char SafetyLevel; // al
  __int64 v106; // rcx
  __int64 v107; // rdx
  unsigned __int64 v108; // rcx
  __int64 v109; // rdx
  _QWORD *v110; // rcx
  int v111; // eax
  __int64 v112; // rdi
  __int64 v113; // rsi
  __int64 v114; // rax
  int v115; // eax
  __int64 *v116; // rcx
  int v117; // edx
  int v118; // edi
  char *v119; // r8
  const char *v120; // r9
  __int64 v121; // rax
  char *i8; // rdx
  __int64 v123; // r8
  __int64 v124; // rax
  __int64 v125; // rbx
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rax
  int v129; // eax
  unsigned __int64 v130; // rdi
  __int64 v131; // rax
  __int64 v132; // rdi
  __int64 v133; // rax
  int v134; // edx
  __int64 v135; // r8
  __int64 v136; // r9
  bool v137; // zf
  __int16 *v138; // rsi
  int v139; // ecx
  int v140; // r15d
  __int64 v141; // r12
  __int16 v142; // ax
  unsigned int v143; // r14d
  int v144; // esi
  __int64 v145; // rdx
  __int64 v146; // r8
  __int16 *v147; // rcx
  __int64 v148; // rax
  __int64 v149; // rax
  _DWORD *v150; // rcx
  const char *v151; // r8
  const char **v152; // rdi
  const char **v153; // rdx
  _QWORD *v154; // rdx
  __int64 v155; // r13
  __int64 v156; // rdx
  _QWORD *v157; // rdi
  __int64 v158; // rax
  __int64 v159; // rcx
  int v160; // r12d
  _QWORD *v161; // rax
  __int64 v162; // r8
  __int64 v163; // r14
  __int64 v164; // rsi
  __int64 v165; // rdi
  __int64 v166; // rcx
  unsigned int v167; // r15d
  _QWORD *v168; // r15
  char *v169; // rax
  const char **v170; // rdi
  int v171; // edx
  const char *v172; // r11
  const char *v173; // r8
  const char *v174; // r9
  unsigned __int8 *i9; // rdx
  __int64 v176; // rax
  __int64 v177; // r8
  bool v178; // cc
  _QWORD *Index; // rdi
  __int64 *v180; // rsi
  __int64 v181; // rax
  __int64 v182; // rdx
  unsigned int v183; // ecx
  _QWORD *jj; // rax
  __int64 v185; // rdx
  unsigned __int16 *v186; // rax
  int v187; // r15d
  int v188; // eax
  unsigned int v189; // esi
  __int64 v190; // r14
  int v191; // edx
  __int64 v192; // rax
  __int64 v193; // rdi
  __int64 v194; // r8
  __int64 v195; // rdx
  _QWORD *kk; // rcx
  __int64 *v197; // rcx
  _QWORD *v198; // rdi
  unsigned int mm; // esi
  unsigned int v200; // esi
  __int64 v201; // rdi
  __int64 v202; // rdx
  __int64 **v203; // rdi
  unsigned int v204; // esi
  __int64 *v205; // r14
  unsigned int v206; // esi
  __int64 v207; // rdi
  _QWORD *ii; // rdi
  _QWORD *v209; // rdi
  char **v210; // rdi
  __int64 v211; // rax
  __int64 v212; // rdi
  __int64 v213; // rcx
  __int64 v214; // rdx
  _QWORD *n; // rax
  unsigned int v216; // r15d
  __int64 *v217; // rcx
  int v218; // esi
  __int64 v219; // r14
  int v220; // eax
  unsigned int v221; // edi
  unsigned int v222; // r13d
  _QWORD *v223; // rcx
  const char **v224; // rsi
  __int64 *v225; // r12
  __int64 v226; // r15
  __int64 v227; // rdx
  unsigned int v228; // r14d
  __int64 v229; // rcx
  _QWORD *k; // rax
  const char **v231; // rax
  __int64 *v232; // rcx
  int v233; // eax
  int v234; // ecx
  __int64 v235; // rsi
  int m; // r12d
  __int64 v237; // rax
  __int64 v238; // r13
  int v239; // eax
  __int64 v240; // rsi
  int v241; // r14d
  int v242; // r12d
  __int64 v243; // rax
  __int64 v244; // r13
  __int64 *v245; // rdx
  unsigned int v246; // r12d
  int v247; // ecx
  _DWORD *v248; // r15
  _DWORD *v249; // r14
  _DWORD *v250; // r9
  __int64 v251; // rcx
  __int64 v252; // rdx
  __int64 v253; // rcx
  int v254; // r12d
  __int64 *v255; // rax
  int *v256; // rbx
  int v257; // edi
  __int64 Function; // rax
  __int64 v259; // rax
  int v260; // r13d
  BOOL v261; // edx
  int v262; // r14d
  __int64 i6; // r12
  __int64 v264; // r9
  __int64 v265; // rax
  signed int v266; // r9d
  int v267; // ecx
  int *v268; // r14
  _QWORD *v269; // rax
  __int64 *v270; // rcx
  int v271; // eax
  int v272; // ecx
  _QWORD *v273; // rdx
  __int64 v274; // rax
  __int64 nn; // rax
  int v276; // eax
  int *v277; // rax
  int v278; // r9d
  __int64 v279; // rdx
  _QWORD *i1; // r10
  __int64 v281; // rcx
  __int64 i2; // rcx
  __int64 v283; // rax
  __int64 v284; // rdi
  __int64 v285; // rax
  __int64 *v286; // rax
  __int64 v287; // rax
  _QWORD *v288; // r12
  __int64 v289; // rdi
  int v290; // r15d
  __int64 i3; // rcx
  _QWORD *v292; // rdi
  _DWORD *v293; // r12
  int v294; // esi
  __int64 v295; // r14
  __int64 *v296; // rax
  __int64 v297; // r12
  __int64 v298; // rax
  const char **v299; // r12
  const char *v300; // r15
  unsigned int TempRange; // eax
  int v302; // edx
  const char *v303; // rdi
  unsigned int v304; // esi
  unsigned int v305; // edi
  int v306; // eax
  __int64 v307; // r8
  int v308; // ecx
  _BYTE *v309; // rdx
  int v310; // eax
  int v311; // r9d
  const char *i4; // rcx
  __int64 *v313; // rax
  __int64 v314; // rdi
  __int64 v315; // rax
  __int64 *v316; // rax
  __int64 *v317; // rax
  int v318; // edi
  unsigned int v319; // r12d
  int v320; // r15d
  int v321; // edx
  __int64 v322; // r14
  int v323; // eax
  int v324; // ecx
  int v325; // edi
  int v326; // r12d
  int v327; // r15d
  __int64 v328; // rax
  const char *v329; // rcx
  __int64 v330; // rdx
  __int64 v331; // rdi
  __int16 v332; // dx
  const char *i5; // rcx
  unsigned int v334; // edx
  char *v335; // r13
  int v336; // eax
  int v337; // esi
  int *v338; // rdx
  _DWORD *v339; // r8
  __int64 v340; // r14
  int v341; // eax
  __int64 v342; // rcx
  __int64 v343; // rax
  __int64 v344; // rax
  __int64 v345; // rsi
  __int64 v346; // rcx
  __int64 v347; // rcx
  __int64 v348; // rax
  unsigned int v349; // edx
  __int64 v350; // rcx
  __int64 v351; // rax
  __int64 v352; // rax
  _DWORD *v353; // r9
  __int64 v354; // rdi
  __int64 v355; // rdx
  int v356; // eax
  __int64 v357; // rcx
  __int64 v358; // rax
  __int64 v359; // rax
  __int64 v360; // rdx
  int v361; // eax
  int *v362; // r9
  __int64 v363; // rcx
  unsigned int v364; // edx
  __int64 v365; // rcx
  __int64 v366; // rax
  __int64 *v367; // rax
  __int64 v368; // rax
  char *v369; // rdi
  __int64 v370; // rcx
  int v371; // edx
  __int64 v372; // rcx
  __int64 v373; // rax
  __int64 v374; // rcx
  __int64 v375; // rax
  int *v376; // r14
  __int64 v377; // rdi
  __int64 v378; // rdx
  __int64 v379; // rcx
  __int64 v380; // rax
  __int64 v381; // rcx
  __int64 v382; // rax
  __int64 v383; // rdx
  char v384; // al
  int v385; // edx
  __int64 v386; // rcx
  __int64 v387; // rcx
  __int64 v388; // rax
  __int64 v389; // rax
  __int64 v390; // rax
  __int64 v391; // rcx
  __int64 v392; // rax
  int v393; // ebx
  __int64 v394; // rax
  __int64 v395; // rax
  __int64 v396; // rax
  __int64 v397; // rcx
  int v398; // edx
  __int64 v399; // rcx
  int v400; // esi
  int v401; // eax
  const char *v402; // rdx
  _QWORD *v403; // rdi
  _DWORD *v404; // rax
  _DWORD *v405; // r12
  __int64 *v406; // rcx
  unsigned int v407; // r14d
  unsigned int v408; // r15d
  int v409; // eax
  __int64 v410; // rdi
  _QWORD *v411; // rsi
  __int64 *v412; // r12
  __int64 v413; // rcx
  int v414; // r14d
  int *v415; // rsi
  __int64 v416; // rax
  __int64 v417; // rdx
  __int64 v418; // rdi
  __int64 v419; // rcx
  __int64 v420; // rax
  __int64 v421; // rax
  __int64 v422; // rdx
  __int64 v423; // rcx
  int v424; // r15d
  __int64 v425; // r12
  unsigned int v426; // esi
  __int64 *v427; // rcx
  int v428; // edi
  int IndexKey; // eax
  int *v430; // r15
  unsigned int v431; // edx
  _DWORD *v432; // r14
  int v433; // r9d
  __int64 v434; // rcx
  __int64 v435; // rcx
  __int64 v436; // rax
  int v437; // edx
  unsigned int v438; // r8d
  __int64 v439; // rsi
  __int64 v440; // rcx
  __int64 v441; // rax
  __int64 v442; // rcx
  __int64 v443; // rcx
  __int64 v444; // rax
  __int64 v445; // rcx
  __int64 v446; // rcx
  __int64 v447; // rax
  unsigned int String; // eax
  __int64 v449; // rcx
  unsigned int v450; // r14d
  __int64 v451; // rcx
  __int64 v452; // rax
  int v453; // eax
  __int64 v454; // rcx
  int v455; // edx
  __int64 *v456; // rcx
  const char **v457; // rax
  _DWORD *v458; // rsi
  unsigned int v459; // edx
  __int64 v460; // rcx
  __int64 v461; // rcx
  __int64 v462; // rax
  __int64 v463; // rdi
  int v464; // edx
  __int64 v465; // rcx
  __int64 v466; // rax
  __int64 v467; // rcx
  __int64 v468; // rcx
  __int64 v469; // rax
  unsigned int v470; // edx
  __int64 v471; // rcx
  __int64 v472; // rcx
  __int64 v473; // rax
  __int64 *v474; // rax
  int v475; // esi
  int v476; // edi
  unsigned int v477; // r15d
  __int64 v478; // r14
  __int64 *v479; // rax
  int *v480; // r8
  __int64 v481; // rcx
  __int64 v482; // rcx
  __int64 v483; // rax
  __int64 v484; // rcx
  int v485; // edx
  __int64 v486; // rcx
  __int64 v487; // rax
  _DWORD *v488; // r14
  __int64 v489; // rdi
  __int64 v490; // rcx
  __int64 v491; // rax
  __int64 v492; // rcx
  int v493; // esi
  __int64 v494; // rcx
  __int64 v495; // rcx
  __int64 v496; // rax
  __int64 v497; // rcx
  unsigned int v498; // edx
  __int64 v499; // rcx
  __int64 v500; // rax
  __int64 *v501; // rax
  __int64 *v502; // rax
  int v503; // r14d
  int v504; // edi
  __int64 v505; // rsi
  __int64 v506; // rcx
  __int64 v507; // rcx
  __int64 v508; // rcx
  __int64 v509; // rax
  unsigned int v510; // edx
  __int64 v511; // rdi
  __int64 v512; // rcx
  __int64 v513; // rax
  __int64 v514; // rcx
  __int64 v515; // rcx
  __int64 v516; // rax
  __int64 *v517; // rax
  _DWORD *v518; // rdi
  int v519; // r8d
  unsigned int v520; // r8d
  __int64 v521; // rcx
  int v522; // edx
  __int64 v523; // rcx
  __int64 v524; // rax
  __int64 v525; // rdx
  __int64 v526; // rcx
  __int64 v527; // rax
  __int64 v528; // rcx
  unsigned int v529; // edx
  __int64 v530; // rcx
  __int64 v531; // rax
  __int64 v532; // rcx
  int v533; // r14d
  __int64 *v534; // rax
  int v535; // r8d
  __int64 v536; // r8
  __int64 v537; // r9
  __int64 v538; // rcx
  int v539; // edi
  __int64 v540; // rcx
  unsigned int v541; // edx
  __int64 v542; // rcx
  __int64 v543; // rax
  __int64 *v544; // rax
  int v545; // eax
  __int64 v546; // rax
  _QWORD *v547; // rsi
  __int64 v548; // rdi
  __int64 v549; // rax
  __int64 *v550; // rax
  __int64 v551; // rax
  __int64 v552; // rcx
  __int64 v553; // rax
  __int64 v554; // rdi
  __int64 v555; // rax
  const char *v556; // r9
  char **v557; // rdi
  char *v558; // rdx
  signed __int64 v559; // r9
  __int64 v560; // rax
  __int64 v561; // r8
  __int64 v562; // rdx
  int v563; // edi
  __int64 v564; // rax
  char *v565; // rcx
  __int64 v566; // rbx
  _DWORD *v567; // rax
  int v568; // ecx
  char **v569; // rdi
  __int64 v570; // r8
  int v571; // edi
  __int64 v572; // r11
  int v573; // eax
  __int64 v574; // r11
  int v575; // edi
  _QWORD *v576; // rdx
  __int64 v577; // rcx
  int v578; // edi
  __int64 v579; // rbx
  __int64 v580; // rax
  int v581; // r14d
  int v582; // edi
  _QWORD *v583; // r12
  int v584; // esi
  __int64 *v585; // r11
  unsigned int v586; // r13d
  int v587; // eax
  int v588; // r14d
  int v589; // r8d
  __int64 v590; // rdx
  __int64 v591; // r9
  __int64 *v592; // rcx
  int v593; // eax
  _QWORD *v594; // r12
  __int64 v595; // r15
  _BYTE *v596; // r8
  int v597; // edx
  const char *v598; // r9
  __int64 v599; // rax
  int v600; // r14d
  __int16 v601; // si
  int v602; // edx
  int v603; // r14d
  __int64 v604; // rax
  __int64 *v605; // r14
  char v606; // cl
  unsigned int v607; // esi
  unsigned __int8 v608; // cl
  __int64 v609; // r8
  __int64 v610; // r9
  __int64 Op; // rax
  int v612; // r9d
  __int64 v613; // rcx
  __int64 v614; // rax
  __int64 v615; // rax
  __int64 v616; // rax
  int v617; // eax
  unsigned __int64 v618; // rax
  char *v619; // rsi
  size_t v620; // rdi
  int v621; // r9d
  char v622; // r8
  char *v623; // r10
  __int64 v624; // rdx
  int v625; // eax
  __int64 v626; // r9
  int v627; // r9d
  const char *v628; // r8
  char *v629; // rdx
  int v630; // edi
  int v631; // [rsp+20h] [rbp-E0h]
  int v632; // [rsp+20h] [rbp-E0h]
  int v633; // [rsp+20h] [rbp-E0h]
  _QWORD *v634; // [rsp+60h] [rbp-A0h]
  unsigned int v635; // [rsp+68h] [rbp-98h] BYREF
  int DbName; // [rsp+6Ch] [rbp-94h]
  __int64 *v637; // [rsp+70h] [rbp-90h]
  int v638; // [rsp+78h] [rbp-88h] BYREF
  const char **v639; // [rsp+80h] [rbp-80h]
  char v640; // [rsp+88h] [rbp-78h]
  unsigned int v641; // [rsp+8Ch] [rbp-74h]
  int *v642; // [rsp+90h] [rbp-70h]
  char *Str; // [rsp+98h] [rbp-68h]
  unsigned int v644; // [rsp+A0h] [rbp-60h]
  _DWORD *v645; // [rsp+A8h] [rbp-58h]
  int v646; // [rsp+B0h] [rbp-50h]
  unsigned int v647; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v648; // [rsp+B8h] [rbp-48h] BYREF
  int v649; // [rsp+C0h] [rbp-40h]
  int v650; // [rsp+C4h] [rbp-3Ch] BYREF
  signed int v651; // [rsp+C8h] [rbp-38h]
  char *v652; // [rsp+D0h] [rbp-30h]
  __int64 Table; // [rsp+D8h] [rbp-28h]
  _QWORD *v654; // [rsp+E0h] [rbp-20h]
  int v655; // [rsp+E8h] [rbp-18h]
  char *v656; // [rsp+F0h] [rbp-10h]
  const char *v657; // [rsp+F8h] [rbp-8h]
  __int64 v658; // [rsp+100h] [rbp+0h]
  int v659; // [rsp+108h] [rbp+8h] BYREF
  BOOL v660; // [rsp+10Ch] [rbp+Ch]
  __int64 v661; // [rsp+110h] [rbp+10h] BYREF
  __int64 v662; // [rsp+118h] [rbp+18h] BYREF
  int v663; // [rsp+120h] [rbp+20h] BYREF
  __int64 v664; // [rsp+128h] [rbp+28h] BYREF
  const char *v665[4]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v666[5]; // [rsp+150h] [rbp+50h] BYREF

  v5 = (char *)a1[2];
  v7 = *a1;
  v637 = a1;
  v634 = (_QWORD *)v7;
  v10 = a1;
  v652 = v5;
  if ( v5 )
  {
    v656 = v5;
  }
  else
  {
    if ( !a1[21] && (*(_BYTE *)(v7 + 96) & 8) == 0 )
      *((_BYTE *)a1 + 35) = 1;
    result = (char *)sqlite3VdbeCreate(a1);
    v652 = result;
    v5 = result;
    v656 = result;
    if ( !result )
      return result;
  }
  v12 = *((int *)v5 + 36);
  if ( *((_DWORD *)v5 + 37) > (int)v12 )
  {
    *((_DWORD *)v5 + 36) = v12 + 1;
    v13 = 3 * v12;
    v14 = *((_QWORD *)v5 + 17);
    v661 = 0;
    *(_QWORD *)(v14 + 8 * v13 + 16) = 0;
    v10 = v637;
    *(_DWORD *)(v14 + 8 * v13) = 166;
    *(_DWORD *)(v14 + 8 * v13 + 4) = 1;
    *(_QWORD *)(v14 + 8 * v13 + 8) = 1;
  }
  else
  {
    v661 = 0;
    growOp3((_DWORD)v5, 166, 1, 1, 0);
  }
  v15 = *v10;
  *((_DWORD *)v10 + 14) = 2;
  if ( *(_DWORD *)(a3 + 8) )
  {
    if ( *(_BYTE *)(v15 + 197) )
      return (char *)sqlite3ErrorMsg(v10, "corrupt database");
    v16 = a3;
    v17 = sqlite3NameFromToken(v15, a2);
    DbName = sqlite3FindDbName(v15, v17);
    v18 = DbName;
    if ( v17 )
    {
      sqlite3DbFreeNN(v15);
      v18 = DbName;
    }
    if ( v18 < 0 )
    {
      _mm_lfence();
      return (char *)sqlite3ErrorMsg(v637, "unknown database %T", a2);
    }
    v10 = v637;
  }
  else
  {
    v18 = *(unsigned __int8 *)(v15 + 196);
    v16 = a2;
    DbName = v18;
  }
  _mm_lfence();
  v19 = v634[4] + 32LL * v18;
  if ( v18 != 1 || (result = (char *)sqlite3OpenTempDatabase(v10), !(_DWORD)result) )
  {
    result = (char *)sqlite3NameFromToken(v634, v16);
    v657 = result;
    v20 = (int)result;
    if ( result )
    {
      if ( a5 )
        v21 = (char *)sqlite3MPrintf(v634, "-%T", a4);
      else
        v21 = (char *)sqlite3NameFromToken(v634, a4);
      Str = v21;
      if ( *(_DWORD *)(a3 + 8) )
      {
        _mm_lfence();
        v22 = *(_QWORD *)v19;
      }
      else
      {
        v22 = 0;
      }
      v23 = v20;
      v639 = (const char **)v22;
      v24 = v637;
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)v637, 19, v23, (_DWORD)v21, v22) )
        goto LABEL_38;
      v665[1] = v657;
      v665[2] = Str;
      v665[0] = 0;
      v665[3] = 0;
      *((_DWORD *)v634 + 162) = 0;
      v25 = sqlite3_file_control(v634, v22, 14, v665);
      if ( !v25 )
      {
        sqlite3VdbeSetNumCols(v5, 1);
        sqlite3VdbeSetColName(v5, 0, 0, v665[0], -1);
        if ( v665[0] )
        {
          sqlite3VdbeLoadString(v5, 1, v665[0]);
          sqlite3VdbeAddOp2(v5, 84, 1, 1);
          v26 = v665[0];
          if ( v665[0] )
          {
            if ( dword_1803379C0 )
            {
              if ( (_QWORD)xmmword_1803DC8D0 )
                xmmword_180337A40(xmmword_1803DC8D0);
              v27 = (*((__int64 (__fastcall **)(const char *))&xmmword_1803379F0 + 1))(v26);
              --qword_1803DC858;
              qword_1803DC810 -= v27;
              (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v26);
              v28 = xmmword_1803DC8D0;
LABEL_36:
              if ( v28 )
                xmmword_180337A50(v28);
            }
            else
            {
              (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v665[0]);
            }
          }
        }
        goto LABEL_38;
      }
      if ( v25 != 12 )
      {
        if ( v665[0] )
        {
          sqlite3ErrorMsg(v24, "%s", v665[0]);
          v30 = v665[0];
          if ( v665[0] )
          {
            if ( dword_1803379C0 )
            {
              if ( (_QWORD)xmmword_1803DC8D0 )
                xmmword_180337A40(xmmword_1803DC8D0);
              v31 = (*((__int64 (__fastcall **)(const char *))&xmmword_1803379F0 + 1))(v30);
              --qword_1803DC858;
              qword_1803DC810 -= v31;
              (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v30);
              if ( (_QWORD)xmmword_1803DC8D0 )
              {
                xmmword_180337A50(xmmword_1803DC8D0);
                ++*((_DWORD *)v24 + 12);
                *((_DWORD *)v24 + 6) = v25;
                goto LABEL_38;
              }
            }
            else
            {
              (*((void (__fastcall **)(const char *))&xmmword_1803379E0 + 1))(v665[0]);
            }
          }
        }
        ++*((_DWORD *)v24 + 12);
        *((_DWORD *)v24 + 6) = v25;
        goto LABEL_38;
      }
      v32 = pragmaLocate(v657);
      v34 = v32;
      if ( !v32 )
        goto LABEL_38;
      v35 = v637;
      if ( (*(_BYTE *)(v32 + 9) & 1) != 0 )
      {
        if ( (unsigned int)sqlite3ReadSchema(v637) )
          goto LABEL_38;
      }
      v36 = *(_BYTE *)(v34 + 9);
      if ( (v36 & 2) == 0 )
      {
        if ( (v36 & 4) != 0 )
        {
          v37 = Str;
          if ( Str )
          {
LABEL_61:
            v38 = DbName;
            v39 = DbName;
            switch ( *(_BYTE *)(v34 + 8) )
            {
              case 0:
                if ( v37 && !(unsigned int)sqlite3DecOrHexToI64(v37, &v648) && v648 >= 0 )
                  *((_DWORD *)v634 + 182) = v648 & 0x7FFFFFFF;
                returnSingleInt(v5, *((int *)v634 + 182));
                goto LABEL_38;
              case 1:
                v563 = *(_DWORD *)(v34 + 16);
                *((_DWORD *)v5 + 51) |= 1 << DbName;
                if ( !v37 || (*(_BYTE *)(v34 + 9) & 8) != 0 )
                {
                  v567 = (_DWORD *)sqlite3VdbeAddOpList(v5, 3, &qword_18026DDD8, 0);
                  v568 = DbName;
                  v567[1] = DbName;
                  v567[7] = v568;
                  v567[9] = v563;
LABEL_964:
                  sqlite3VdbeReusable(v5);
                  goto LABEL_38;
                }
                v564 = sqlite3VdbeAddOpList(v5, 2, &qword_18026DDD0, 0);
                v565 = Str;
                v566 = v564;
                v663 = 0;
                LODWORD(v564) = DbName;
                *(_DWORD *)(v566 + 4) = DbName;
                *(_DWORD *)(v566 + 28) = v564;
                *(_DWORD *)(v566 + 32) = v563;
                sqlite3GetInt32(v565, &v663);
                *(_DWORD *)(v566 + 36) = v663;
                *(_WORD *)(v566 + 26) = 1;
                if ( v563 != 1 )
                  goto LABEL_38;
                v29 = v634;
                if ( (v634[6] & 0x10000000) != 0 )
                  *(_BYTE *)(v566 + 24) = -69;
                goto LABEL_39;
              case 2:
                v82 = *(_QWORD *)(v19 + 8);
                if ( !v37 )
                {
                  v83 = *(_QWORD *)(v82 + 8);
                  v84 = 0;
                  if ( *(_BYTE *)(v83 + 33) )
                  {
                    LOBYTE(v84) = *(_BYTE *)(v83 + 34) != 0;
                    ++v84;
                  }
                  returnSingleInt(v5, v84);
                  goto LABEL_38;
                }
                v85 = v37;
                while ( 2 )
                {
                  v86 = (unsigned __int8)*v85;
                  v87 = (unsigned __int8)v85["none" - v37];
                  if ( (_BYTE)v86 == (_BYTE)v87 )
                  {
                    if ( !(_BYTE)v86 )
                    {
                      v88 = 0;
                      goto LABEL_185;
                    }
                  }
                  else if ( *((unsigned __int8 *)qword_18026E880 + v86) != *((unsigned __int8 *)qword_18026E880 + v87) )
                  {
                    for ( i = v37; ; ++i )
                    {
                      v90 = (unsigned __int8)*i;
                      v91 = (unsigned __int8)i["full" - v37];
                      if ( (_BYTE)v90 == (_BYTE)v91 )
                      {
                        if ( !(_BYTE)v90 )
                        {
                          v88 = 1;
                          goto LABEL_185;
                        }
                      }
                      else if ( *((unsigned __int8 *)qword_18026E880 + v90) != *((unsigned __int8 *)qword_18026E880 + v91) )
                      {
                        for ( j = v37; ; ++j )
                        {
                          v93 = (unsigned __int8)*j;
                          v94 = (unsigned __int8)j["incremental" - v37];
                          if ( (_BYTE)v93 == (_BYTE)v94 )
                          {
                            if ( !(_BYTE)v93 )
                            {
                              v88 = 2;
                              goto LABEL_185;
                            }
                          }
                          else if ( *((unsigned __int8 *)qword_18026E880 + v93) != *((unsigned __int8 *)qword_18026E880
                                                                                   + v94) )
                          {
                            v635 = 0;
                            sqlite3GetInt32(v37, &v635);
                            v95 = v635;
                            if ( v635 > 2 )
                              v95 = 0;
                            v88 = v95;
LABEL_185:
                            v29 = v634;
                            *((_BYTE *)v634 + 106) = v88;
                            if ( !(unsigned int)sqlite3BtreeSetAutoVacuum(v82, v88) && v88 - 1 <= 1 )
                            {
                              v96 = *((_DWORD *)v5 + 36);
                              v97 = (_DWORD *)sqlite3VdbeAddOpList(v5, 5, qword_18026DC08, 0);
                              v98 = DbName;
                              v97[14] = v96 + 4;
                              v97[27] = v88 - 1;
                              v97[1] = v98;
                              v97[7] = v98;
                              v97[25] = v98;
                              *((_DWORD *)v5 + 51) |= 1 << v98;
                            }
LABEL_39:
                            _mm_lfence();
                            sqlite3DbFreeNN(v29);
                            result = Str;
                            if ( Str )
                              return (char *)sqlite3DbFreeNN(v634);
                            return result;
                          }
                        }
                      }
                    }
                  }
                  ++v85;
                  continue;
                }
              case 3:
                if ( v37 )
                {
                  v29 = v634;
                  v130 = *(_QWORD *)(v34 + 16) & 0xFFFFFFFFFFFFBFFFuLL;
                  if ( *((_BYTE *)v634 + 101) )
                    v130 = *(_QWORD *)(v34 + 16);
                  if ( (unsigned __int8)getSafetyLevel(v37, 1, 0) )
                  {
                    if ( (v130 & 1) == 0 || (v634[6] & 0x10000000) == 0 )
                      v634[6] |= v130;
                  }
                  else
                  {
                    v634[6] &= ~v130;
                    if ( v130 == 0x80000 )
                    {
                      v634[94] = 0;
                    }
                    else if ( (v130 & 1) != 0 && !(unsigned int)sqlite3StrICmp(Str, "reset") )
                    {
                      sqlite3ResetAllSchemasOfConnection(v634);
                    }
                  }
                  sqlite3VdbeAddOp0(v5, 166);
                  setAllPagerFlags(v634);
                }
                else
                {
                  setPragmaResultColumnNames(v5, v34);
                  v29 = v634;
                  returnSingleInt(v5, (v634[6] & *(_QWORD *)(v34 + 16)) != 0);
                }
                goto LABEL_39;
              case 5:
                if ( v37 )
                {
                  v635 = 0;
                  sqlite3GetInt32(Str, &v635);
                  *(_DWORD *)(*(_QWORD *)(v19 + 24) + 116LL) = v635;
                  sqlite3BtreeSetCacheSize(*(_QWORD *)(v19 + 8), *(unsigned int *)(*(_QWORD *)(v19 + 24) + 116LL));
                }
                else
                {
                  returnSingleInt(v5, *(int *)(*(_QWORD *)(v19 + 24) + 116LL));
                }
                goto LABEL_38;
              case 6:
                if ( !v37 )
                {
                  v29 = v634;
                  if ( (v634[6] & 0x20) != 0 )
                  {
                    v101 = sqlite3BtreeSetSpillSize(*(_QWORD *)(v19 + 8), 0);
                    returnSingleInt(v5, v101);
                  }
                  else
                  {
                    returnSingleInt(v5, 0);
                  }
                  goto LABEL_39;
                }
                v635 = 1;
                Int32 = sqlite3GetInt32(v37, &v635);
                v104 = v635;
                if ( Int32 )
                  sqlite3BtreeSetSpillSize(*(_QWORD *)(v19 + 8), v635);
                LOBYTE(v103) = v104 != 0;
                SafetyLevel = getSafetyLevel(Str, 1, v103);
                v106 = v634[6];
                v107 = v106 | 0x20;
                v108 = v106 & 0xFFFFFFFFFFFFFFDFuLL;
                if ( !SafetyLevel )
                  v107 = v108;
                v634[6] = v107;
                setAllPagerFlags(v634);
                goto LABEL_38;
              case 7:
                if ( !v37 )
                  goto LABEL_38;
                v256 = &dword_18026E3BC;
                v257 = 12;
                if ( !(unsigned __int8)getSafetyLevel(v37, 1, 0) )
                {
                  v256 = (int *)byte_18026E3B8;
                  v257 = 4;
                }
                _mm_lfence();
                sqlite3CreateFunc(
                  (_DWORD)v634,
                  (unsigned int)"like",
                  2,
                  1,
                  (__int64)v256,
                  (__int64)likeFunc,
                  0,
                  0,
                  0,
                  0,
                  0);
                LOBYTE(v632) = 0;
                Function = sqlite3FindFunction(v634, "like", 2, 1, v632);
                *(_DWORD *)(Function + 4) = (*(_DWORD *)(Function + 4) | v257) & 0xFFDFFFFF;
                sqlite3CreateFunc(
                  (_DWORD)v634,
                  (unsigned int)"like",
                  3,
                  1,
                  (__int64)v256,
                  (__int64)likeFunc,
                  0,
                  0,
                  0,
                  0,
                  0);
                LOBYTE(v633) = 0;
                v259 = sqlite3FindFunction(v634, "like", 3, 1, v633);
                v29 = v634;
                *(_DWORD *)(v259 + 4) = (*(_DWORD *)(v259 + 4) | v257) & 0xFFDFFFFF;
                goto LABEL_39;
              case 8:
                v29 = v634;
                *((_DWORD *)v637 + 14) = 2;
                v203 = (__int64 **)v634[77];
                if ( !v203 )
                  goto LABEL_39;
                v204 = 0;
                do
                {
                  sqlite3VdbeMultiLoad(v5, 1, "is", v204, *v203[2]);
                  v203 = (__int64 **)*v203;
                  ++v204;
                }
                while ( v203 );
                goto LABEL_38;
              case 9:
                v569 = off_18026E6E0;
                *((_DWORD *)v637 + 14) = 1;
                while ( (unsigned __int64)v661 <= 0x33 )
                {
                  v570 = (__int64)*v569++;
                  ++v661;
                  if ( !v570 )
                    break;
                  sqlite3VdbeLoadString(v5, 1, v570);
                  sqlite3VdbeAddOp2(v5, 84, 1, 1);
                }
                goto LABEL_964;
              case 0xA:
                if ( (_BYTE)word_1803379C4 )
                {
                  v128 = xmmword_180337A30(11);
                  if ( v128 )
                    xmmword_180337A40(v128);
                }
                if ( !Str )
                {
                  returnSingleText(v5, sqlite3_data_directory);
                  v29 = v634;
                  goto LABEL_250;
                }
                v29 = v634;
                if ( *Str
                  && ((*(unsigned int (__fastcall **)(_QWORD, char *, __int64, int *))(*v634 + 56LL))(
                        *v634,
                        Str,
                        1,
                        &v663)
                   || !v663) )
                {
                  goto LABEL_249;
                }
                sqlite3_free(sqlite3_data_directory);
                if ( *Str )
                  sqlite3_data_directory = sqlite3_mprintf("%s", Str);
                else
                  sqlite3_data_directory = 0;
                goto LABEL_250;
              case 0xB:
                v154 = v634;
                *((_DWORD *)v637 + 14) = 3;
                if ( *((int *)v634 + 10) <= 0 )
                  goto LABEL_387;
                v200 = 0;
                v201 = 0;
                do
                {
                  v202 = v154[4];
                  if ( *(_QWORD *)(v202 + v201 + 8) )
                    sqlite3VdbeMultiLoad(v5, 1, "iss", v200, *(_QWORD *)(v202 + v201));
                  v154 = v634;
                  ++v200;
                  v201 += 32;
                }
                while ( (signed int)v200 < *((_DWORD *)v634 + 10) );
                v29 = v634;
                goto LABEL_39;
              case 0xD:
                if ( v37 )
                {
                  v29 = v634;
                  if ( (*((_BYTE *)v634 + 44) & 0x40) != 0 )
                    goto LABEL_39;
                  v556 = "UTF8";
                  v557 = &off_18026DD40;
                  if ( !"UTF8" )
                  {
LABEL_952:
                    if ( *v557 )
                      goto LABEL_39;
                    goto LABEL_953;
                  }
LABEL_946:
                  v558 = v37;
                  v559 = v556 - v37;
                  while ( 1 )
                  {
                    v560 = (unsigned __int8)*v558;
                    v561 = (unsigned __int8)v558[v559];
                    if ( (_BYTE)v560 == (_BYTE)v561 )
                    {
                      if ( !(_BYTE)v560 )
                      {
                        v562 = 2;
                        if ( *((_BYTE *)v557 + 8) )
                          v562 = *((unsigned __int8 *)v557 + 8);
                        *(_BYTE *)(*(_QWORD *)(v634[4] + 24LL) + 113LL) = v562;
                        sqlite3SetTextEncoding(v634, v562);
                        v37 = Str;
                        goto LABEL_952;
                      }
                    }
                    else if ( *((unsigned __int8 *)qword_18026E880 + v560) != *((unsigned __int8 *)qword_18026E880 + v561) )
                    {
                      v556 = v557[2];
                      v557 += 2;
                      if ( !v556 )
                      {
LABEL_953:
                        sqlite3ErrorMsg(v35, "unsupported encoding: %s", v37);
                        goto LABEL_39;
                      }
                      goto LABEL_946;
                    }
                    ++v558;
                  }
                }
                if ( !(unsigned int)sqlite3ReadSchema(v637) )
                  returnSingleText(v5, (&off_18026DD40)[2 * *(unsigned __int8 *)(*v637 + 100)]);
                goto LABEL_38;
              case 0xE:
                _mm_lfence();
                v220 = *((_DWORD *)v637 + 14);
                v221 = v220 + 5;
                v222 = v220 + 1;
                *((_DWORD *)v637 + 14) = v220 + 5;
                v644 = v220 + 1;
                v635 = v220 + 5;
                v223 = *(_QWORD **)(*(_QWORD *)(32 * v38 + v634[4] + 24) + 16LL);
                if ( !v223 )
                  goto LABEL_38;
                v224 = v639;
                do
                {
                  v225 = v637;
                  if ( v37 )
                  {
                    Table = sqlite3LocateTable(v637, 0, v37, v224);
                    v226 = Table;
                    v223 = 0;
                  }
                  else
                  {
                    v226 = v223[2];
                    v223 = (_QWORD *)*v223;
                    Table = v226;
                  }
                  v654 = v223;
                  if ( v226 && !*(_BYTE *)(v226 + 63) && *(_QWORD *)(v226 + 72) )
                  {
                    v227 = *(_QWORD *)(v226 + 96);
                    v228 = -32768;
                    v229 = -32768;
                    if ( v227 )
                    {
                      v228 = 0;
                      v229 = 0;
                      for ( k = (_QWORD *)(v634[4] + 24LL); *k != v227; ++v229 )
                      {
                        ++v228;
                        k += 4;
                      }
                    }
                    v231 = *(const char ***)(32 * v229 + v634[4]);
                    v232 = v637;
                    v639 = v231;
                    if ( v637[21] )
                      v232 = (__int64 *)v637[21];
                    v233 = *((_DWORD *)v232 + 33);
                    if ( !_bittest(&v233, v228) )
                    {
                      *((_DWORD *)v232 + 33) = v233 | (1 << v228);
                      if ( v228 == 1 )
                        sqlite3OpenTempDatabase(v232);
                    }
                    v234 = v221 + *(__int16 *)(v226 + 54);
                    if ( *((_DWORD *)v225 + 14) < v234 )
                      *((_DWORD *)v225 + 14) = v234;
                    sqlite3OpenTable((_DWORD)v225, 0, v228, v226, 112);
                    sqlite3VdbeLoadString(v5, v222, *(_QWORD *)v226);
                    v235 = *(_QWORD *)(v226 + 72);
                    for ( m = 1; v235; ++m )
                    {
                      v237 = sqlite3FindTable(v634, *(_QWORD *)(v235 + 16), v639);
                      v648 = v237;
                      if ( v237 )
                      {
                        v664 = 0;
                        if ( (unsigned int)sqlite3FkLocateIndex((_DWORD)v637, v237, v235, (unsigned int)&v664, 0) )
                          goto LABEL_38;
                        v238 = v664;
                        if ( v664 )
                        {
                          sqlite3VdbeAddOp3((_DWORD)v5, 112, m, *(_DWORD *)(v664 + 88), v228);
                          sqlite3VdbeSetP4KeyInfo(v637, v238);
                        }
                        else
                        {
                          sqlite3OpenTable((_DWORD)v637, m, v228, v648, 112);
                        }
                      }
                      v235 = *(_QWORD *)(v235 + 8);
                    }
                    if ( *((_DWORD *)v637 + 13) < m )
                      *((_DWORD *)v637 + 13) = m;
                    v239 = sqlite3VdbeAddOp1(v5, 36, 0);
                    v240 = *(_QWORD *)(v226 + 72);
                    v241 = 1;
                    v663 = v239;
                    v242 = v239;
                    LODWORD(v662) = 1;
                    if ( v240 )
                    {
                      do
                      {
                        v243 = sqlite3FindTable(v634, *(_QWORD *)(v240 + 16), v639);
                        v648 = v243;
                        v664 = 0;
                        v244 = 0;
                        v661 = 0;
                        if ( v243 )
                        {
                          sqlite3FkLocateIndex((_DWORD)v637, v243, v240, (unsigned int)&v664, (__int64)&v661);
                          v244 = v661;
                        }
                        v245 = v637;
                        --*((_DWORD *)v637 + 17);
                        v246 = *((_DWORD *)v245 + 17);
                        v247 = v221 + *(_DWORD *)(v240 + 40);
                        if ( *((_DWORD *)v245 + 14) < v247 )
                          *((_DWORD *)v245 + 14) = v247;
                        if ( *(int *)(v240 + 40) > 0 )
                        {
                          v248 = (_DWORD *)v244;
                          v249 = (_DWORD *)(v240 + 64);
                          do
                          {
                            v250 = v249;
                            if ( v244 )
                              v250 = v248;
                            sqlite3ExprCodeGetColumnOfTable((_DWORD)v5, Table, 0, *v250, v221);
                            sqlite3VdbeAddOp2(v5, 50, v221++, v246);
                            v249 += 4;
                            ++v248;
                          }
                          while ( (signed int)(v221 - v635) < *(_DWORD *)(v240 + 40) );
                          v221 = v635;
                          v226 = Table;
                          v241 = v662;
                        }
                        if ( v664 )
                        {
                          v251 = *(_QWORD *)(v664 + 32);
                          if ( !v251 )
                            v251 = computeIndexAffStr(v634, v664);
                          sqlite3VdbeAddOp4(
                            (_DWORD)v5,
                            96,
                            v221,
                            *(_DWORD *)(v240 + 40),
                            0,
                            v251,
                            *(_DWORD *)(v240 + 40));
                          sqlite3VdbeAddOp4Int((_DWORD)v5, 29, v241, v246, v221, *(_DWORD *)(v240 + 40));
                        }
                        else if ( v648 )
                        {
                          sqlite3VdbeAddOp3((_DWORD)v5, 30, v241, *((_DWORD *)v5 + 36) + 2, v221);
                          sqlite3VdbeGoto(v5, v246);
                        }
                        v252 = 135;
                        if ( *(char *)(v226 + 48) < 0 )
                          v252 = 75;
                        sqlite3VdbeAddOp2(v5, v252, 0, v644 + 1);
                        sqlite3VdbeMultiLoad(v5, v644 + 2, "siX", *(_QWORD *)(v240 + 16), v241 - 1);
                        sqlite3VdbeAddOp2(v5, 84, v644, 4);
                        v253 = *((_QWORD *)v5 + 3);
                        v254 = ~v246;
                        if ( *(_DWORD *)(v253 + 68) + *(_DWORD *)(v253 + 72) >= 0 )
                          *(_DWORD *)(*(_QWORD *)(v253 + 80) + 4LL * v254) = *((_DWORD *)v5 + 36);
                        else
                          resizeResolveLabel(v253, v5, (unsigned int)v254);
                        if ( v244 )
                          sqlite3DbFreeNN(v634);
                        v240 = *(_QWORD *)(v240 + 8);
                        LODWORD(v662) = ++v241;
                      }
                      while ( v240 );
                      v242 = v663;
                    }
                    sqlite3VdbeAddOp2(v5, 39, 0, (unsigned int)(v242 + 1));
                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                      v255 = &qword_1803DCAC0;
                    else
                      v255 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * v242);
                    v222 = v644;
                    v223 = v654;
                    v224 = v639;
                    *((_DWORD *)v255 + 2) = *((_DWORD *)v5 + 36);
                  }
                  v37 = Str;
                }
                while ( v223 );
                goto LABEL_38;
              case 0xF:
                if ( v37 )
                {
                  v211 = sqlite3FindTable(v634, v37, v639);
                  if ( v211 )
                  {
                    if ( !*(_BYTE *)(v211 + 63) )
                    {
                      v212 = *(_QWORD *)(v211 + 72);
                      if ( v212 )
                      {
                        v213 = *(_QWORD *)(v211 + 96);
                        v214 = -32768;
                        if ( v213 )
                        {
                          v214 = 0;
                          for ( n = (_QWORD *)(v634[4] + 24LL); *n != v213; n += 4 )
                            v214 = (unsigned int)(v214 + 1);
                        }
                        v216 = 0;
                        v217 = v637;
                        *((_DWORD *)v637 + 14) = 8;
                        sqlite3CodeVerifySchema(v217, v214);
                        do
                        {
                          v218 = 0;
                          if ( *(int *)(v212 + 40) > 0 )
                          {
                            v219 = v212 + 64;
                            do
                            {
                              actionName(*(unsigned __int8 *)(v212 + 45));
                              actionName(*(unsigned __int8 *)(v212 + 46));
                              sqlite3VdbeMultiLoad(v5, 1, "iissssss", v216, v218++);
                              v219 += 16;
                            }
                            while ( v218 < *(_DWORD *)(v212 + 40) );
                          }
                          v212 = *(_QWORD *)(v212 + 8);
                          ++v216;
                        }
                        while ( v212 );
                      }
                    }
                  }
                }
                goto LABEL_38;
              case 0x10:
                v205 = &qword_1803DC750;
                v661 = (__int64)&qword_1803DC750;
                v206 = (*((_DWORD *)v634 + 11) >> 5) & 1;
                *((_DWORD *)v637 + 14) = 6;
                do
                {
                  v207 = *v205;
                  if ( *v205 )
                  {
                    do
                    {
                      pragmaFunclistLine(v5, v207, 1, v206);
                      v207 = *(_QWORD *)(v207 + 64);
                    }
                    while ( v207 );
                    v205 = (__int64 *)v661;
                  }
                  v661 = (__int64)++v205;
                }
                while ( (__int64)v205 < (__int64)&qword_1803DC808 );
                v29 = v634;
                for ( ii = (_QWORD *)v634[74]; ii; ii = (_QWORD *)*ii )
                  pragmaFunclistLine(v5, ii[2], 0, v206);
                goto LABEL_39;
              case 0x11:
                if ( v37 )
                {
                  if ( !(unsigned int)sqlite3DecOrHexToI64(v37, &v648) )
                  {
                    v615 = sqlite3_hard_heap_limit64(-1);
                    if ( v648 > 0 && (!v615 || v615 > v648) )
                      sqlite3_hard_heap_limit64(v648);
                  }
                }
                v616 = sqlite3_hard_heap_limit64(-1);
                returnSingleInt(v5, v616);
                goto LABEL_38;
              case 0x12:
                v635 = 0;
                if ( !Str || !(unsigned int)sqlite3GetInt32(Str, &v635) || (v99 = v635, (int)v635 <= 0) )
                  v99 = 0x7FFFFFFF;
                sqlite3BeginWriteOperation(v35, 0, (unsigned int)DbName);
                sqlite3VdbeAddOp2(v5, 71, v99, 1);
                v100 = sqlite3VdbeAddOp1(v5, 62, (unsigned int)DbName);
                sqlite3VdbeAddOp1(v5, 84, 1);
                sqlite3VdbeAddOp2(v5, 86, 1, 0xFFFFFFFFLL);
                sqlite3VdbeAddOp2(v5, 59, 1, v100);
                sqlite3VdbeJumpHere(v5, v100);
                goto LABEL_38;
              case 0x13:
                if ( !v37 )
                  goto LABEL_38;
                Index = (_QWORD *)sqlite3FindIndex(v634, v37, v639);
                if ( Index )
                {
                  v180 = v637;
                }
                else
                {
                  v180 = v637;
                  v181 = sqlite3LocateTable(v637, 2, Str, v639);
                  if ( !v181 )
                    goto LABEL_38;
                  if ( *(char *)(v181 + 48) >= 0 )
                    goto LABEL_38;
                  Index = (_QWORD *)sqlite3PrimaryKeyIndex(v181);
                  if ( !Index )
                    goto LABEL_38;
                }
                v182 = Index[6];
                v183 = -32768;
                if ( v182 )
                {
                  v183 = 0;
                  for ( jj = (_QWORD *)(v634[4] + 24LL); *jj != v182; jj += 4 )
                    ++v183;
                }
                v185 = *(_QWORD *)(v34 + 16);
                v186 = (unsigned __int16 *)(Index + 12);
                if ( !v185 )
                  v186 = (unsigned __int16 *)Index + 47;
                v187 = *v186;
                v188 = 6;
                if ( !v185 )
                  v188 = 3;
                *((_DWORD *)v180 + 14) = v188;
                sqlite3CodeVerifySchema(v180, v183);
                v189 = 0;
                if ( v187 )
                {
                  v190 = 0;
                  do
                  {
                    v191 = *(__int16 *)(Index[1] + 2 * v190);
                    if ( (v191 & 0x8000u) == 0 )
                      _mm_lfence();
                    sqlite3VdbeMultiLoad(v5, 1, "iisX", v189, v191);
                    if ( *(_QWORD *)(v34 + 16) )
                      sqlite3VdbeMultiLoad(
                        v5,
                        4,
                        "isiX",
                        *(unsigned __int8 *)(Index[7] + v190),
                        *(_QWORD *)(Index[8] + 8 * v190));
                    sqlite3VdbeAddOp2(v5, 84, 1, *((unsigned int *)v637 + 14));
                    ++v189;
                    ++v190;
                  }
                  while ( (int)v189 < v187 );
                }
                goto LABEL_38;
              case 0x14:
                if ( v37 )
                {
                  v192 = sqlite3FindTable(v634, v37, v639);
                  v193 = v192;
                  if ( v192 )
                  {
                    v194 = *(_QWORD *)(v192 + 96);
                    v195 = -32768;
                    if ( v194 )
                    {
                      v195 = 0;
                      for ( kk = (_QWORD *)(v634[4] + 24LL); *kk != v194; kk += 4 )
                        v195 = (unsigned int)(v195 + 1);
                    }
                    v197 = v637;
                    *((_DWORD *)v637 + 14) = 5;
                    sqlite3CodeVerifySchema(v197, v195);
                    v198 = *(_QWORD **)(v193 + 16);
                    for ( mm = 0; v198; ++mm )
                    {
                      v666[0] = "c";
                      v666[1] = "u";
                      v666[2] = "pk";
                      sqlite3VdbeMultiLoad(v5, 1, "isisi", mm, *v198);
                      v198 = (_QWORD *)v198[5];
                    }
                  }
                }
                goto LABEL_38;
              case 0x15:
                v260 = 0;
                v664 = 0;
                v655 = 100;
                v650 = 100;
                v137 = *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v657) == 113;
                v640 = *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v657);
                v261 = v137;
                v137 = *(_QWORD *)a3 == 0;
                v660 = v261;
                v262 = 100;
                if ( v137 )
                  LODWORD(v38) = -1;
                *((_DWORD *)v637 + 14) = 6;
                DbName = v38;
                if ( v37 )
                {
                  if ( (unsigned int)sqlite3GetInt32(*a4, &v650) )
                  {
                    v262 = v650;
                    i6 = 0;
                    v655 = v650;
                    if ( v650 <= 0 )
                    {
                      v262 = 100;
                      v655 = 100;
                    }
                  }
                  else
                  {
                    if ( DbName < 0 )
                    {
                      v264 = 0;
                    }
                    else
                    {
                      _mm_lfence();
                      v264 = *(_QWORD *)(32LL * DbName + v634[4]);
                    }
                    v265 = sqlite3LocateTable(v35, 0, Str, v264);
                    v262 = v650;
                    i6 = v265;
                    v664 = v265;
                    v655 = v650;
                  }
                }
                else
                {
                  i6 = 0;
                }
                sqlite3VdbeAddOp2(v5, 71, (unsigned int)(v262 - 1), 1);
                v266 = 0;
                v651 = 0;
                if ( *((int *)v634 + 10) <= 0 )
                  goto LABEL_938;
                v267 = DbName;
                v268 = (int *)(v5 + 144);
                v645 = v5 + 148;
                v269 = v634;
                v642 = (int *)(v5 + 144);
                while ( 1 )
                {
                  if ( v267 < 0 || v266 == v267 )
                  {
                    v270 = v35;
                    if ( v35[21] )
                      v270 = (__int64 *)v35[21];
                    v271 = *((_DWORD *)v270 + 33);
                    if ( !_bittest(&v271, v266) )
                    {
                      *((_DWORD *)v270 + 33) = v271 | (1 << v266);
                      if ( v266 == 1 )
                      {
                        sqlite3OpenTempDatabase(v270);
                        v266 = v651;
                      }
                    }
                    *((_BYTE *)v35 + 35) = 0;
                    v272 = 0;
                    Table = *(_QWORD *)(32LL * v266 + v634[4] + 24);
                    v273 = *(_QWORD **)(Table + 16);
                    if ( !v273 )
                      goto LABEL_934;
                    do
                    {
                      v274 = v273[2];
                      if ( !i6 || i6 == v274 )
                      {
                        if ( *(char *)(v274 + 48) >= 0 )
                          ++v272;
                        for ( nn = *(_QWORD *)(v274 + 16); nn; ++v272 )
                          nn = *(_QWORD *)(nn + 40);
                      }
                      v273 = (_QWORD *)*v273;
                    }
                    while ( v273 );
                    if ( v272 )
                    {
                      v276 = v272 + 1;
                      if ( !i6 )
                        v276 = v272;
                      v277 = (int *)sqlite3DbMallocRawNN(v634, 4LL * v276 + 4);
                      if ( !v277 )
                      {
LABEL_937:
                        v262 = v655;
LABEL_938:
                        v555 = sqlite3VdbeAddOpList(v5, 7, qword_18026DCC8, 0);
                        if ( v555 )
                        {
                          *(_BYTE *)(v555 + 49) = -1;
                          *(_DWORD *)(v555 + 8) = 1 - v262;
                          *(_BYTE *)(v555 + 121) = -1;
                          *(_QWORD *)(v555 + 64) = "ok";
                          *(_QWORD *)(v555 + 136) = "database disk image is malformed";
                        }
                        sqlite3VdbeChangeP3(v5, 0, (unsigned int)(*((_DWORD *)v5 + 36) - 2));
                        goto LABEL_38;
                      }
                      v278 = 0;
                      v279 = 0;
                      if ( i6 )
                      {
                        v278 = 1;
                        v277[1] = 0;
                        v279 = 1;
                      }
                      for ( i1 = *(_QWORD **)(Table + 16); i1; i1 = (_QWORD *)*i1 )
                      {
                        v281 = i1[2];
                        if ( !i6 || i6 == v281 )
                        {
                          if ( *(char *)(v281 + 48) >= 0 )
                          {
                            ++v278;
                            v277[++v279] = *(_DWORD *)(v281 + 40);
                          }
                          for ( i2 = *(_QWORD *)(v281 + 16); i2; i2 = *(_QWORD *)(i2 + 40) )
                          {
                            ++v279;
                            ++v278;
                            v277[v279] = *(_DWORD *)(i2 + 88);
                          }
                        }
                      }
                      *v277 = v278;
                      if ( *((_DWORD *)v35 + 14) < v278 + 8 )
                        *((_DWORD *)v35 + 14) = v278 + 8;
                      *((_BYTE *)v35 + 31) = 0;
                      *((_DWORD *)v35 + 10) = 0;
                      sqlite3VdbeAddOp4((_DWORD)v5, 155, 1, v278, 8, (__int64)v277, -14);
                      v283 = *v268;
                      if ( (int)v283 > 0 )
                        *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v283 - 22) = (unsigned __int8)v651;
                      v284 = (int)sqlite3VdbeAddOp1(v5, 50, 2);
                      v285 = sqlite3MPrintf(v634, "*** in database %s ***\n", *(const char **)(32LL * v651 + v634[4]));
                      sqlite3VdbeAddOp4((_DWORD)v5, 117, 0, 3, 0, v285, -6);
                      sqlite3VdbeAddOp3((_DWORD)v5, 111, 2, 3, 3);
                      integrityCheckResultRow(v5);
                      if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                        v286 = &qword_1803DCAC0;
                      else
                        v286 = (__int64 *)(*((_QWORD *)v5 + 17) + 24 * v284);
                      *((_DWORD *)v286 + 2) = *v268;
                      LOBYTE(v260) = i6 != 0;
                      sqlite3VdbeLoadString(v5, 2, "wrong # of entries in index ");
                      v287 = Table;
                      v288 = *(_QWORD **)(Table + 16);
                      v661 = (__int64)v288;
                      if ( v288 )
                      {
                        do
                        {
                          v289 = v288[2];
                          if ( !v664 || v664 == v289 )
                          {
                            v290 = v260;
                            if ( *(char *)(v289 + 48) < 0 )
                            {
                              for ( i3 = *(_QWORD *)(v289 + 16); i3; ++v290 )
                              {
                                if ( (*(_DWORD *)(i3 + 100) & 3) == 2 )
                                  break;
                                i3 = *(_QWORD *)(i3 + 40);
                              }
                            }
                            else
                            {
                              ++v260;
                            }
                            v292 = *(_QWORD **)(v289 + 16);
                            if ( v292 )
                            {
                              v293 = v642;
                              v294 = v260 + 8;
                              do
                              {
                                if ( !v292[9] )
                                {
                                  v295 = (int)sqlite3VdbeAddOp3((_DWORD)v5, 53, v294, 0, v290 + 8);
                                  sqlite3VdbeLoadString(v5, 4, *v292);
                                  sqlite3VdbeAddOp3((_DWORD)v5, 111, 4, 2, 3);
                                  integrityCheckResultRow(v5);
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                    v296 = &qword_1803DCAC0;
                                  else
                                    v296 = (__int64 *)(*((_QWORD *)v5 + 17) + 24 * v295);
                                  *((_DWORD *)v296 + 2) = *v293;
                                }
                                v292 = (_QWORD *)v292[5];
                                ++v260;
                                ++v294;
                              }
                              while ( v292 );
                              v288 = (_QWORD *)v661;
                            }
                          }
                          v288 = (_QWORD *)*v288;
                          v661 = (__int64)v288;
                        }
                        while ( v288 );
                        v268 = v642;
                        v35 = v637;
                        v287 = Table;
                      }
                      v297 = *(_QWORD *)(v287 + 16);
                      v260 = 0;
                      v648 = v297;
                      if ( v297 )
                      {
                        v298 = v664;
                        do
                        {
                          v299 = *(const char ***)(v297 + 16);
                          v639 = v299;
                          v658 = 0;
                          v646 = -1;
                          if ( (!v298 || (const char **)v298 == v299) && !*((_BYTE *)v299 + 63) )
                          {
                            if ( v640 == 113 || *((char *)v299 + 48) >= 0 )
                            {
                              v300 = 0;
                              v654 = 0;
                              v644 = 0;
                            }
                            else
                            {
                              v300 = v299[2];
                              v654 = v300;
                              if ( v300 )
                              {
                                do
                                {
                                  if ( (*((_DWORD *)v300 + 25) & 3) == 2 )
                                    break;
                                  v300 = (const char *)*((_QWORD *)v300 + 5);
                                }
                                while ( v300 );
                                v654 = v300;
                              }
                              TempRange = sqlite3GetTempRange(v35, *((unsigned __int16 *)v300 + 47));
                              v302 = *((unsigned __int16 *)v300 + 47) - 1;
                              v644 = TempRange;
                              sqlite3VdbeAddOp3((_DWORD)v5, 75, 1, TempRange, TempRange + v302);
                            }
                            sqlite3OpenTableAndIndices(
                              (_DWORD)v35,
                              (_DWORD)v299,
                              112,
                              0,
                              1,
                              0,
                              (__int64)&v647,
                              (__int64)&v638);
                            sqlite3VdbeAddOp2(v5, 71, 0, 7);
                            v303 = v299[2];
                            if ( v303 )
                            {
                              v304 = 8;
                              do
                              {
                                sqlite3VdbeAddOp2(v5, 71, 0, v304);
                                v303 = (const char *)*((_QWORD *)v303 + 5);
                                ++v304;
                              }
                              while ( v303 );
                            }
                            v305 = v647;
                            sqlite3VdbeAddOp2(v5, 36, v647, 0);
                            v306 = sqlite3VdbeAddOp2(v5, 86, 7, 1);
                            v137 = *((_BYTE *)v299 + 48) >= 0;
                            v663 = v306;
                            if ( v137 )
                            {
                              v307 = (unsigned int)*((__int16 *)v299 + 27);
                              v308 = -1;
                              if ( (int)v307 > 0 )
                              {
                                v309 = v299[1] + 18;
                                do
                                {
                                  v137 = (*v309 & 0x20) == 0;
                                  v310 = v308 + 1;
                                  v309 += 24;
                                  if ( !v137 )
                                    v310 = v308;
                                  v308 = v310;
                                  --v307;
                                }
                                while ( v307 );
                              }
                              v311 = v308 - 1;
                              if ( v308 != *((__int16 *)v299 + 26) )
                                v311 = v308;
                            }
                            else
                            {
                              for ( i4 = v299[2]; i4; i4 = (const char *)*((_QWORD *)i4 + 5) )
                              {
                                if ( (*((_DWORD *)i4 + 25) & 3) == 2 )
                                  break;
                              }
                              v311 = *((unsigned __int16 *)i4 + 48) - 1;
                            }
                            if ( v311 >= 0 )
                            {
                              _mm_lfence();
                              sqlite3VdbeAddOp3((_DWORD)v5, 94, v305, v311, 3);
                              v313 = *(_BYTE *)(*(_QWORD *)v5 + 103LL)
                                   ? &qword_1803DCAC0
                                   : (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (*v268 - 1));
                              if ( *((_DWORD *)v313 + 3) == 3 && *(_BYTE *)v313 == 94 )
                                *((_WORD *)v313 + 1) |= 0x80u;
                            }
                            if ( v640 != 113 && v300 )
                            {
                              v314 = (int)sqlite3VdbeAddOp4Int(
                                            (_DWORD)v5,
                                            41,
                                            v305,
                                            0,
                                            v644,
                                            *((unsigned __int16 *)v300 + 47));
                              sqlite3VdbeAddOp1(v5, 50, v644);
                              v315 = sqlite3MPrintf(v634, "row not in PRIMARY KEY order for %s", *v299);
                              sqlite3VdbeAddOp4((_DWORD)v5, 117, 0, 3, 0, v315, -6);
                              integrityCheckResultRow(v5);
                              v316 = *(_BYTE *)(*(_QWORD *)v5 + 103LL)
                                   ? &qword_1803DCAC0
                                   : (__int64 *)(*((_QWORD *)v5 + 17) + 24 * v314);
                              *((_DWORD *)v316 + 2) = *v268;
                              v317 = *(_BYTE *)(*(_QWORD *)v5 + 103LL)
                                   ? &qword_1803DCAC0
                                   : (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * ((int)v314 + 1));
                              *((_DWORD *)v317 + 2) = *v268;
                              v318 = 0;
                              if ( *((_WORD *)v300 + 47) )
                              {
                                v319 = v647;
                                do
                                {
                                  sqlite3ExprCodeLoadIndexColumn((_DWORD)v637, (_DWORD)v300, v319, v318, v318 + v644);
                                  ++v318;
                                }
                                while ( v318 < *((unsigned __int16 *)v300 + 47) );
                                v5 = v652;
                                v299 = v639;
                              }
                            }
                            v320 = 0;
                            v321 = (_DWORD)v299[6] & 0x10000;
                            v641 = 0;
                            v635 = v321;
                            if ( *((__int16 *)v299 + 27) > 0 )
                            {
                              while ( 1 )
                              {
                                v322 = (__int64)&v299[1][24 * v320];
                                v323 = *((__int16 *)v299 + 26);
                                v661 = v322;
                                if ( v320 == v323 )
                                  goto LABEL_752;
                                v324 = 0;
                                LOBYTE(v324) = v321
                                             ? (*(_DWORD *)(v322 + 8) & 0xF0u) > 0x10
                                             : *(_BYTE *)(v322 + 12) > 65;
                                v137 = (*(_BYTE *)(v322 + 8) & 0xF) == 0;
                                v650 = v324;
                                if ( v137 && !v324 )
                                  goto LABEL_752;
                                v137 = (*(_BYTE *)(v322 + 18) & 0x20) == 0;
                                v325 = 5;
                                v649 = 5;
                                if ( v137 )
                                {
                                  v328 = *(unsigned __int16 *)(v322 + 16);
                                  if ( (_WORD)v328 )
                                  {
                                    v137 = *((_BYTE *)v299 + 63) == 0;
                                    v662 = 0;
                                    if ( v137 )
                                    {
                                      v329 = v299[10];
                                      if ( v329 )
                                      {
                                        if ( *(_DWORD *)v329 >= (int)v328 )
                                        {
                                          v330 = *(_QWORD *)&v329[32 * v328 - 24];
                                          if ( v330 )
                                          {
                                            valueFromExpr(
                                              (_DWORD)v634,
                                              v330,
                                              *((unsigned __int8 *)v634 + 100),
                                              *(unsigned __int8 *)(v322 + 12),
                                              (__int64)&v662,
                                              0);
                                            v331 = v662;
                                            if ( v662 )
                                            {
                                              v332 = *(_WORD *)(v662 + 20);
                                              v649 = *((unsigned __int8 *)qword_18026F2C0 + (v332 & 0x3F));
                                              if ( (v332 & 0x9000) != 0 || *(_DWORD *)(v662 + 32) )
                                                vdbeMemClear(v662);
                                              sqlite3DbFreeNN(*(_QWORD *)(v331 + 24));
                                            }
                                            v325 = v649;
                                          }
                                        }
                                      }
                                    }
                                  }
                                  v326 = v647;
                                  if ( *((char *)v639 + 48) >= 0 )
                                  {
                                    v327 = (__int16)sqlite3TableColumnToStorage(v639, (unsigned __int16)v320);
                                  }
                                  else
                                  {
                                    for ( i5 = v639[2]; i5; i5 = (const char *)*((_QWORD *)i5 + 5) )
                                    {
                                      if ( (*((_DWORD *)i5 + 25) & 3) == 2 )
                                        break;
                                    }
                                    v334 = 0;
                                    if ( *((_WORD *)i5 + 48) )
                                    {
                                      while ( (_WORD)v320 != *(_WORD *)(*((_QWORD *)i5 + 1) + 2LL * v334) )
                                      {
                                        if ( (int)++v334 >= *((unsigned __int16 *)i5 + 48) )
                                          goto LABEL_661;
                                      }
                                    }
                                    else
                                    {
LABEL_661:
                                      LOWORD(v334) = -1;
                                    }
                                    v327 = (__int16)v334;
                                  }
                                }
                                else
                                {
                                  sqlite3ExprCodeGetColumnOfTable((_DWORD)v5, (_DWORD)v299, v647, v320, 3);
                                  v326 = -1;
                                  v327 = 3;
                                }
                                v335 = v5;
                                v336 = *((_DWORD *)v637 + 17) - 1;
                                LODWORD(v662) = v336;
                                v337 = v336 - 1;
                                *((_DWORD *)v637 + 17) = v336 - 1;
                                v137 = (*(_BYTE *)(v322 + 8) & 0xF) == 0;
                                LODWORD(v652) = v336 - 1;
                                if ( v137 )
                                {
                                  v362 = v642;
                                }
                                else
                                {
                                  v338 = v642;
                                  v339 = v645;
                                  v340 = *v642;
                                  if ( *v645 > (int)v340 )
                                  {
                                    v342 = 3 * v340;
                                    *v642 = v340 + 1;
                                    v343 = *((_QWORD *)v5 + 17);
                                    *(_DWORD *)(v343 + 8 * v342) = 64786;
                                    *(_DWORD *)(v343 + 8 * v342 + 4) = v326;
                                    *(_DWORD *)(v343 + 8 * v342 + 8) = v337;
                                    *(_DWORD *)(v343 + 8 * v342 + 12) = v327;
                                    *(_DWORD *)(v343 + 8 * v342 + 16) = v325;
                                  }
                                  else
                                  {
                                    v341 = addOp4IntSlow((_DWORD)v5, 18, v326, v337, v327, v325);
                                    v338 = v642;
                                    LODWORD(v340) = v341;
                                    v339 = v645;
                                  }
                                  v344 = *((int *)v656 + 36);
                                  if ( v326 >= 0 )
                                  {
                                    if ( (int)v344 > 0 )
                                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v344 - 22) = 13;
                                    v346 = *v338;
                                    if ( *v339 > (int)v346 )
                                    {
                                      *v338 = v346 + 1;
                                      v347 = 3 * v346;
                                      v348 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v348 + 8 * v347) = 94;
                                      *(_DWORD *)(v348 + 8 * v347 + 4) = v326;
                                      *(_DWORD *)(v348 + 8 * v347 + 8) = v327;
                                      *(_DWORD *)(v348 + 8 * v347 + 12) = 3;
                                      *(_QWORD *)(v348 + 8 * v347 + 16) = 0;
                                    }
                                    else
                                    {
                                      _mm_lfence();
                                      growOp3((_DWORD)v5, 94, v326, v327, 3);
                                    }
                                    sqlite3ColumnDefault(v5, v639, v641, 3);
                                    v345 = *v642;
                                    if ( *v645 > (int)v345 )
                                    {
                                      v349 = (unsigned int)v652;
                                      *v642 = v345 + 1;
                                      v350 = 3 * v345;
                                      v351 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v351 + 8 * v350) = 51;
                                      *(_DWORD *)(v351 + 8 * v350 + 4) = 3;
                                      *(_QWORD *)(v351 + 8 * v350 + 8) = v349;
                                      *(_QWORD *)(v351 + 8 * v350 + 16) = 0;
                                    }
                                    else
                                    {
                                      LODWORD(v345) = growOp3((_DWORD)v5, 51, 3, (_DWORD)v652, 0);
                                    }
                                  }
                                  else
                                  {
                                    if ( (int)v344 > 0 )
                                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v344 - 22) = 15;
                                    LODWORD(v345) = v340;
                                  }
                                  v352 = sqlite3MPrintf(v634, "NULL value in %s.%s", *v639, *(const char **)v661);
                                  v353 = v642;
                                  v354 = v352;
                                  v355 = *v642;
                                  if ( *v645 > (int)v355 )
                                  {
                                    v357 = 3 * v355;
                                    *v642 = v355 + 1;
                                    v358 = *((_QWORD *)v5 + 17);
                                    *(_QWORD *)(v358 + 8 * v357) = 117;
                                    *(_QWORD *)(v358 + 8 * v357 + 8) = 3;
                                    *(_QWORD *)(v358 + 8 * v357 + 16) = 0;
                                  }
                                  else
                                  {
                                    v356 = growOp3((_DWORD)v5, 117, 0, 3, 0);
                                    v353 = v642;
                                    LODWORD(v355) = v356;
                                  }
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                  {
                                    if ( v354 )
                                      sqlite3DbNNFreeNN(*(_QWORD *)v5, v354);
                                  }
                                  else
                                  {
                                    if ( (int)v355 < 0 )
                                    {
                                      _mm_lfence();
                                      LODWORD(v355) = *v353 - 1;
                                    }
                                    v359 = *((_QWORD *)v5 + 17);
                                    v137 = *(_BYTE *)(v359 + 24LL * (int)v355 + 1) == 0;
                                    v360 = v359 + 24LL * (int)v355;
                                    if ( v137 )
                                    {
                                      if ( v354 )
                                      {
                                        *(_QWORD *)(v360 + 16) = v354;
                                        *(_BYTE *)(v360 + 1) = -6;
                                      }
                                    }
                                    else
                                    {
                                      vdbeChangeP4Full(v5, v360, v354, 4294967290LL);
                                    }
                                  }
                                  v361 = v650;
                                  v362 = v642;
                                  if ( !v650 )
                                  {
                                    v337 = (int)v652;
                                    v322 = v661;
                                    goto LABEL_705;
                                  }
                                  v363 = *v642;
                                  if ( *v645 > (int)v363 )
                                  {
                                    v364 = v662;
                                    *v642 = v363 + 1;
                                    v365 = 3 * v363;
                                    v366 = *((_QWORD *)v5 + 17);
                                    *(_QWORD *)(v366 + 8 * v365) = 9;
                                    *(_QWORD *)(v366 + 8 * v365 + 8) = v364;
                                    *(_QWORD *)(v366 + 8 * v365 + 16) = 0;
                                  }
                                  else
                                  {
                                    growOp3((_DWORD)v5, 9, 0, v662, 0);
                                    v362 = v642;
                                  }
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                    v367 = &qword_1803DCAC0;
                                  else
                                    v367 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v340);
                                  *((_DWORD *)v367 + 2) = *v362;
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                  {
                                    v337 = (int)v652;
                                    v322 = v661;
                                    dword_1803DCAC8 = *v362;
                                  }
                                  else
                                  {
                                    v322 = v661;
                                    v368 = (int)v345;
                                    v337 = (int)v652;
                                    *(_DWORD *)(*((_QWORD *)v5 + 17) + 24 * v368 + 8) = *v362;
                                  }
                                }
                                v361 = v650;
LABEL_705:
                                v369 = v656;
                                if ( v635 )
                                {
                                  if ( v361 )
                                  {
                                    v370 = *v362;
                                    v371 = v649;
                                    if ( *v645 > (int)v370 )
                                    {
                                      *v362 = v370 + 1;
                                      v372 = 3 * v370;
                                      v373 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v373 + 8 * v372) = 64786;
                                      *(_DWORD *)(v373 + 8 * v372 + 4) = v326;
                                      *(_DWORD *)(v373 + 8 * v372 + 8) = v337;
                                      *(_DWORD *)(v373 + 8 * v372 + 12) = v327;
                                      *(_DWORD *)(v373 + 8 * v372 + 16) = v371;
                                    }
                                    else
                                    {
                                      addOp4IntSlow((_DWORD)v5, 18, v326, v337, v327, v649);
                                      v362 = v642;
                                    }
                                    v374 = *v362;
                                    v260 = 0;
                                    if ( (int)v374 > 0 )
                                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v374 - 22) = *((unsigned __int8 *)&qword_180339BF0
                                                                                          + ((*(_DWORD *)(v322 + 8) >> 4)
                                                                                           & 0xFu)
                                                                                          - 1);
                                    v299 = v639;
                                    v320 = v641;
                                    v375 = sqlite3MPrintf(
                                             v634,
                                             "non-%s value in %s.%s",
                                             off_180337B90[((*(_DWORD *)(v322 + 8) >> 4) & 0xFu) - 1],
                                             *v639,
                                             *(const char **)&v639[1][24 * v641]);
                                    v376 = v642;
                                    v377 = v375;
                                    v378 = *v642;
                                    if ( *v645 > (int)v378 )
                                    {
                                      v379 = 3 * v378;
                                      *v642 = v378 + 1;
                                      v380 = *((_QWORD *)v5 + 17);
                                      *(_QWORD *)(v380 + 8 * v379) = 117;
                                      *(_QWORD *)(v380 + 8 * v379 + 8) = 3;
                                      *(_QWORD *)(v380 + 8 * v379 + 16) = 0;
                                    }
                                    else
                                    {
                                      LODWORD(v378) = growOp3((_DWORD)v5, 117, 0, 3, 0);
                                    }
                                    v381 = *(_QWORD *)v5;
                                    if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                      goto LABEL_718;
LABEL_716:
                                    if ( v377 )
                                      sqlite3DbNNFreeNN(v381, v377);
                                    goto LABEL_745;
                                  }
                                }
                                else
                                {
                                  v384 = *(_BYTE *)(v322 + 12);
                                  if ( v384 == 66 )
                                  {
                                    v376 = v642;
                                    v385 = v649;
                                    v386 = *v642;
                                    if ( *v645 > (int)v386 )
                                    {
                                      *v642 = v386 + 1;
                                      v387 = 3 * v386;
                                      v388 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v388 + 8 * v387) = 64786;
                                      *(_DWORD *)(v388 + 8 * v387 + 4) = v326;
                                      *(_DWORD *)(v388 + 8 * v387 + 8) = v337;
                                      *(_DWORD *)(v388 + 8 * v387 + 12) = v327;
                                      *(_DWORD *)(v388 + 8 * v387 + 16) = v385;
                                    }
                                    else
                                    {
                                      addOp4IntSlow((_DWORD)v5, 18, v326, v337, v327, v649);
                                    }
                                    v389 = *v376;
                                    v260 = 0;
                                    if ( (int)v389 > 0 )
                                      *(_WORD *)(*((_QWORD *)v5 + 17) + 24 * v389 - 22) = 28;
                                    v299 = v639;
                                    v320 = v641;
                                    v390 = sqlite3MPrintf(
                                             v634,
                                             "NUMERIC value in %s.%s",
                                             *v639,
                                             *(const char **)&v639[1][24 * v641]);
                                    v378 = *v376;
                                    v377 = v390;
                                    if ( *v645 > (int)v378 )
                                    {
                                      v391 = 3 * v378;
                                      *v376 = v378 + 1;
                                      v392 = *((_QWORD *)v5 + 17);
                                      *(_QWORD *)(v392 + 8 * v391) = 117;
                                      *(_QWORD *)(v392 + 8 * v391 + 8) = 3;
                                      *(_QWORD *)(v392 + 8 * v391 + 16) = 0;
                                    }
                                    else
                                    {
                                      LODWORD(v378) = growOp3((_DWORD)v5, 117, 0, 3, 0);
                                    }
                                    v381 = *(_QWORD *)v5;
                                    if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                    {
LABEL_718:
                                      if ( (int)v378 < 0 )
                                      {
                                        _mm_lfence();
                                        LODWORD(v378) = *v376 - 1;
                                      }
                                      v382 = *((_QWORD *)v5 + 17);
                                      v137 = *(_BYTE *)(v382 + 24LL * (int)v378 + 1) == 0;
                                      v383 = v382 + 24LL * (int)v378;
                                      if ( v137 )
                                      {
                                        if ( v377 )
                                        {
                                          *(_QWORD *)(v383 + 16) = v377;
                                          *(_BYTE *)(v383 + 1) = -6;
                                        }
                                      }
                                      else
                                      {
                                        vdbeChangeP4Full(v5, v383, v377, 4294967290LL);
                                      }
                                      goto LABEL_745;
                                    }
                                    goto LABEL_716;
                                  }
                                  if ( v384 >= 67 )
                                  {
                                    v393 = v649;
                                    sqlite3VdbeAddOp4Int((_DWORD)v335, 18, v326, v337, v327, v649);
                                    v394 = *v642;
                                    if ( (int)v394 > 0 )
                                      *(_WORD *)(*((_QWORD *)v335 + 17) + 24 * v394 - 22) = 27;
                                    v320 = v641;
                                    if ( v326 >= 0 )
                                      sqlite3ExprCodeGetColumnOfTable((_DWORD)v335, (_DWORD)v639, v647, v641, 3);
                                    sqlite3VdbeAddOp4((_DWORD)v335, 96, 3, 1, 0, (__int64)"C", -1);
                                    sqlite3VdbeAddOp4Int((_DWORD)v335, 18, -1, v337, 3, v393);
                                    v395 = *v642;
                                    if ( (int)v395 > 0 )
                                      *(_WORD *)(*((_QWORD *)v335 + 17) + 24 * v395 - 22) = 28;
                                    v396 = sqlite3MPrintf(
                                             v634,
                                             "TEXT value in %s.%s",
                                             *v639,
                                             *(const char **)&v639[1][24 * v320]);
                                    sqlite3VdbeAddOp4((_DWORD)v335, 117, 0, 3, 0, v396, -6);
                                    v5 = v335;
                                    v656 = v369;
                                    goto LABEL_744;
                                  }
                                }
                                v320 = v641;
LABEL_744:
                                v376 = v642;
                                v260 = 0;
                                v299 = v639;
LABEL_745:
                                v397 = *((_QWORD *)v5 + 3);
                                v398 = ~(_DWORD)v662;
                                if ( *(_DWORD *)(v397 + 68) + *(_DWORD *)(v397 + 72) >= 0 )
                                  *(_DWORD *)(*(_QWORD *)(v397 + 80) + 4LL * v398) = *v376;
                                else
                                  resizeResolveLabel(v397, v5, (unsigned int)v398);
                                integrityCheckResultRow(v5);
                                v399 = *((_QWORD *)v5 + 3);
                                v400 = ~v337;
                                if ( *(_DWORD *)(v399 + 68) + *(_DWORD *)(v399 + 72) >= 0 )
                                  *(_DWORD *)(*(_QWORD *)(v399 + 80) + 4LL * v400) = *v376;
                                else
                                  resizeResolveLabel(v399, v5, (unsigned int)v400);
                                v321 = v635;
LABEL_752:
                                v401 = *((__int16 *)v299 + 27);
                                v641 = ++v320;
                                if ( v320 >= v401 )
                                {
                                  v652 = v5;
                                  break;
                                }
                              }
                            }
                            v402 = v299[4];
                            if ( v402 )
                            {
                              v403 = v634;
                              if ( (v634[6] & 0x200LL) == 0 )
                              {
                                v404 = (_DWORD *)sqlite3ExprListDup(v634, v402, 0);
                                v137 = *((_BYTE *)v634 + 103) == 0;
                                v405 = v404;
                                v661 = (__int64)v404;
                                if ( v137 )
                                {
                                  v406 = v637;
                                  v407 = *((_DWORD *)v637 + 17) - 1;
                                  *((_DWORD *)v637 + 16) = v647 + 1;
                                  v408 = v407 - 1;
                                  *((_DWORD *)v406 + 17) = v407 - 1;
                                  v409 = *v404 - 1;
                                  v410 = v409;
                                  if ( *v405 - 1 > 0 )
                                  {
                                    v411 = &v405[8 * v409 + 2];
                                    v412 = v406;
                                    do
                                    {
                                      sqlite3ExprIfFalse(v412, *v411, v407, 0);
                                      --v410;
                                      v411 -= 4;
                                    }
                                    while ( v410 > 0 );
                                    v405 = (_DWORD *)v661;
                                    v406 = v637;
                                  }
                                  sqlite3ExprIfTrue(v406, *((_QWORD *)v405 + 1), v408, 16);
                                  v413 = *((_QWORD *)v5 + 3);
                                  v414 = ~v407;
                                  if ( *(_DWORD *)(v413 + 68) + *(_DWORD *)(v413 + 72) >= 0 )
                                  {
                                    v415 = v642;
                                    *(_DWORD *)(*(_QWORD *)(v413 + 80) + 4LL * v414) = *v642;
                                  }
                                  else
                                  {
                                    resizeResolveLabel(v413, v5, (unsigned int)v414);
                                    v415 = v642;
                                  }
                                  *((_DWORD *)v637 + 16) = 0;
                                  v416 = sqlite3MPrintf(v634, "CHECK constraint failed in %s", *v639);
                                  v417 = *v415;
                                  v418 = v416;
                                  if ( *v645 > (int)v417 )
                                  {
                                    v419 = 3 * v417;
                                    *v415 = v417 + 1;
                                    v420 = *((_QWORD *)v5 + 17);
                                    *(_QWORD *)(v420 + 8 * v419) = 117;
                                    *(_QWORD *)(v420 + 8 * v419 + 8) = 3;
                                    *(_QWORD *)(v420 + 8 * v419 + 16) = 0;
                                  }
                                  else
                                  {
                                    LODWORD(v417) = growOp3((_DWORD)v5, 117, 0, 3, 0);
                                  }
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                  {
                                    if ( v418 )
                                      sqlite3DbNNFreeNN(*(_QWORD *)v5, v418);
                                  }
                                  else
                                  {
                                    if ( (int)v417 < 0 )
                                    {
                                      _mm_lfence();
                                      LODWORD(v417) = *v415 - 1;
                                    }
                                    v421 = *((_QWORD *)v5 + 17);
                                    v137 = *(_BYTE *)(v421 + 24LL * (int)v417 + 1) == 0;
                                    v422 = v421 + 24LL * (int)v417;
                                    if ( v137 )
                                    {
                                      if ( v418 )
                                      {
                                        *(_QWORD *)(v422 + 16) = v418;
                                        *(_BYTE *)(v422 + 1) = -6;
                                      }
                                    }
                                    else
                                    {
                                      vdbeChangeP4Full(v5, v422, v418, 4294967290LL);
                                    }
                                  }
                                  integrityCheckResultRow(v5);
                                  v423 = *((_QWORD *)v5 + 3);
                                  v424 = ~v408;
                                  if ( *(_DWORD *)(v423 + 68) + *(_DWORD *)(v423 + 72) >= 0 )
                                    *(_DWORD *)(*(_QWORD *)(v423 + 80) + 4LL * v424) = *v415;
                                  else
                                    resizeResolveLabel(v423, v5, (unsigned int)v424);
                                  v403 = v634;
                                }
                                if ( v405 )
                                  exprListDeleteNN(v403);
                                v299 = v639;
                              }
                            }
                            if ( v640 != 113 )
                            {
                              v425 = (__int64)v299[2];
                              v426 = 0;
                              v641 = 0;
                              if ( v425 )
                              {
                                v427 = v637;
                                do
                                {
                                  v428 = *((_DWORD *)v427 + 17) - 1;
                                  *((_DWORD *)v427 + 17) = v428;
                                  if ( v654 != (_QWORD *)v425 )
                                  {
                                    IndexKey = sqlite3GenerateIndexKey(
                                                 (_DWORD)v427,
                                                 v425,
                                                 v647,
                                                 0,
                                                 0,
                                                 (__int64)&v659,
                                                 v658,
                                                 v646);
                                    v430 = v642;
                                    v431 = v426 + 8;
                                    v432 = v645;
                                    v433 = IndexKey;
                                    v646 = IndexKey;
                                    v658 = v425;
                                    v434 = *v642;
                                    if ( *v645 > (int)v434 )
                                    {
                                      *v642 = v434 + 1;
                                      v435 = 3 * v434;
                                      v436 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v436 + 8 * v435) = 86;
                                      *(_DWORD *)(v436 + 8 * v435 + 4) = v431;
                                      *(_QWORD *)(v436 + 8 * v435 + 8) = 1;
                                      *(_QWORD *)(v436 + 8 * v435 + 16) = 0;
                                    }
                                    else
                                    {
                                      growOp3((_DWORD)v5, 86, v431, 1, 0);
                                      v433 = v646;
                                    }
                                    v437 = *(unsigned __int16 *)(v425 + 96);
                                    v438 = v426 + v638;
                                    v439 = *v430;
                                    if ( *v432 > (int)v439 )
                                    {
                                      v440 = 3 * v439;
                                      *v430 = v439 + 1;
                                      v441 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v441 + 8 * v440) = 64797;
                                      *(_DWORD *)(v441 + 8 * v440 + 4) = v438;
                                      *(_DWORD *)(v441 + 8 * v440 + 8) = v428;
                                      *(_DWORD *)(v441 + 8 * v440 + 12) = v433;
                                      *(_DWORD *)(v441 + 8 * v440 + 16) = v437;
                                    }
                                    else
                                    {
                                      LODWORD(v439) = addOp4IntSlow((_DWORD)v5, 29, v438, v428, v433, v437);
                                    }
                                    sqlite3VdbeLoadString(v5, 3, "row ");
                                    v442 = *v430;
                                    if ( *v432 > (int)v442 )
                                    {
                                      *v430 = v442 + 1;
                                      v443 = 3 * v442;
                                      v444 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v444 + 8 * v443) = 111;
                                      *(_DWORD *)(v444 + 8 * v443 + 4) = 7;
                                      *(_DWORD *)(v444 + 8 * v443 + 8) = 3;
                                      *(_DWORD *)(v444 + 8 * v443 + 12) = 3;
                                      *(_QWORD *)(v444 + 8 * v443 + 16) = 0;
                                    }
                                    else
                                    {
                                      growOp3((_DWORD)v5, 111, 7, 3, 3);
                                    }
                                    sqlite3VdbeLoadString(v5, 4, " missing from index ");
                                    v445 = *v430;
                                    if ( *v432 > (int)v445 )
                                    {
                                      *v430 = v445 + 1;
                                      v446 = 3 * v445;
                                      v447 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v447 + 8 * v446) = 111;
                                      *(_DWORD *)(v447 + 8 * v446 + 4) = 4;
                                      *(_DWORD *)(v447 + 8 * v446 + 8) = 3;
                                      *(_DWORD *)(v447 + 8 * v446 + 12) = 3;
                                      *(_QWORD *)(v447 + 8 * v446 + 16) = 0;
                                    }
                                    else
                                    {
                                      growOp3((_DWORD)v5, 111, 4, 3, 3);
                                    }
                                    String = sqlite3VdbeLoadString(v5, 4, *(_QWORD *)v425);
                                    v449 = *v430;
                                    v450 = String;
                                    v635 = String;
                                    if ( *v645 > (int)v449 )
                                    {
                                      *v430 = v449 + 1;
                                      v451 = 3 * v449;
                                      v452 = *((_QWORD *)v5 + 17);
                                      *(_DWORD *)(v452 + 8 * v451) = 111;
                                      *(_DWORD *)(v452 + 8 * v451 + 4) = 4;
                                      *(_DWORD *)(v452 + 8 * v451 + 8) = 3;
                                      *(_DWORD *)(v452 + 8 * v451 + 12) = 3;
                                      *(_QWORD *)(v452 + 8 * v451 + 16) = 0;
                                    }
                                    else
                                    {
                                      growOp3((_DWORD)v5, 111, 4, 3, 3);
                                    }
                                    v453 = integrityCheckResultRow(v5);
                                    v454 = *(_QWORD *)v5;
                                    v455 = *v430;
                                    LODWORD(v662) = v453;
                                    if ( *(_BYTE *)(v454 + 103) )
                                      v456 = &qword_1803DCAC0;
                                    else
                                      v456 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v439);
                                    v457 = v639;
                                    *((_DWORD *)v456 + 2) = v455;
                                    if ( *((char *)v457 + 48) >= 0 )
                                    {
                                      v458 = v645;
                                      v459 = v638 + v641;
                                      v460 = *v430;
                                      if ( *v645 > (int)v460 )
                                      {
                                        *v430 = v460 + 1;
                                        v461 = 3 * v460;
                                        v462 = *((_QWORD *)v5 + 17);
                                        *(_DWORD *)(v462 + 8 * v461) = 142;
                                        *(_DWORD *)(v462 + 8 * v461 + 4) = v459;
                                        *(_QWORD *)(v462 + 8 * v461 + 8) = 3;
                                        *(_QWORD *)(v462 + 8 * v461 + 16) = 0;
                                      }
                                      else
                                      {
                                        growOp3((_DWORD)v5, 142, v459, 3, 0);
                                      }
                                      v463 = *v430;
                                      v464 = *(unsigned __int16 *)(v425 + 96) + v646 - 1;
                                      if ( *v458 > (int)v463 )
                                      {
                                        v465 = 3 * v463;
                                        *v430 = v463 + 1;
                                        v466 = *((_QWORD *)v5 + 17);
                                        *(_DWORD *)(v466 + 8 * v465) = 53;
                                        *(_QWORD *)(v466 + 8 * v465 + 4) = 3;
                                        *(_DWORD *)(v466 + 8 * v465 + 12) = v464;
                                        *(_QWORD *)(v466 + 8 * v465 + 16) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v463) = growOp3((_DWORD)v5, 53, 3, 0, v464);
                                      }
                                      sqlite3VdbeLoadString(v5, 3, "rowid not at end-of-record for row ");
                                      v467 = *v430;
                                      if ( *v645 > (int)v467 )
                                      {
                                        *v430 = v467 + 1;
                                        v468 = 3 * v467;
                                        v469 = *((_QWORD *)v5 + 17);
                                        *(_DWORD *)(v469 + 8 * v468) = 111;
                                        *(_DWORD *)(v469 + 8 * v468 + 4) = 7;
                                        *(_DWORD *)(v469 + 8 * v468 + 8) = 3;
                                        *(_DWORD *)(v469 + 8 * v468 + 12) = 3;
                                        *(_QWORD *)(v469 + 8 * v468 + 16) = 0;
                                      }
                                      else
                                      {
                                        growOp3((_DWORD)v5, 111, 7, 3, 3);
                                      }
                                      sqlite3VdbeLoadString(v5, 4, " of index ");
                                      v470 = v450 - 1;
                                      v471 = *v430;
                                      if ( *v645 > (int)v471 )
                                      {
                                        *v430 = v471 + 1;
                                        v472 = 3 * v471;
                                        v473 = *((_QWORD *)v5 + 17);
                                        *(_QWORD *)(v473 + 8 * v472) = 9;
                                        *(_DWORD *)(v473 + 8 * v472 + 8) = v470;
                                        *(_DWORD *)(v473 + 8 * v472 + 12) = 0;
                                        *(_QWORD *)(v473 + 8 * v472 + 16) = 0;
                                      }
                                      else
                                      {
                                        growOp3((_DWORD)v5, 9, 0, v470, 0);
                                      }
                                      if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                        v474 = &qword_1803DCAC0;
                                      else
                                        v474 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v463);
                                      *((_DWORD *)v474 + 2) = *v430;
                                    }
                                    v475 = 0;
                                    v476 = 0;
                                    if ( *(_WORD *)(v425 + 94) )
                                    {
                                      v477 = v638 + v641;
                                      v478 = 0;
                                      do
                                      {
                                        if ( *(char **)(v478 + *(_QWORD *)(v425 + 64)) != "BINARY" )
                                        {
                                          if ( !v475 )
                                          {
                                            v479 = v637;
                                            --*((_DWORD *)v637 + 17);
                                            v475 = *((_DWORD *)v479 + 17);
                                          }
                                          v480 = v642;
                                          v481 = *v642;
                                          if ( *v645 > (int)v481 )
                                          {
                                            *v642 = v481 + 1;
                                            v482 = 3 * v481;
                                            v483 = *((_QWORD *)v5 + 17);
                                            *(_DWORD *)(v483 + 8 * v482) = 94;
                                            *(_DWORD *)(v483 + 8 * v482 + 4) = v477;
                                            *(_DWORD *)(v483 + 8 * v482 + 8) = v476;
                                            *(_DWORD *)(v483 + 8 * v482 + 12) = 3;
                                            *(_QWORD *)(v483 + 8 * v482 + 16) = 0;
                                          }
                                          else
                                          {
                                            growOp3((_DWORD)v5, 94, v477, v476, 3);
                                            v480 = v642;
                                          }
                                          v484 = *v480;
                                          v485 = v476 + v646;
                                          if ( *v645 > (int)v484 )
                                          {
                                            *v480 = v484 + 1;
                                            v486 = 3 * v484;
                                            v487 = *((_QWORD *)v5 + 17);
                                            *(_DWORD *)(v487 + 8 * v486) = 52;
                                            *(_DWORD *)(v487 + 8 * v486 + 4) = 3;
                                            *(_DWORD *)(v487 + 8 * v486 + 8) = v475;
                                            *(_DWORD *)(v487 + 8 * v486 + 12) = v485;
                                            *(_QWORD *)(v487 + 8 * v486 + 16) = 0;
                                          }
                                          else
                                          {
                                            growOp3((_DWORD)v5, 52, 3, v475, v485);
                                          }
                                        }
                                        ++v476;
                                        v478 += 8;
                                      }
                                      while ( v476 < *(unsigned __int16 *)(v425 + 94) );
                                      v430 = v642;
                                      if ( v475 )
                                      {
                                        v488 = v645;
                                        v489 = *v642;
                                        if ( *v645 > (int)v489 )
                                        {
                                          v490 = 3 * v489;
                                          *v642 = v489 + 1;
                                          v491 = *((_QWORD *)v5 + 17);
                                          *(_QWORD *)(v491 + 8 * v490) = 9;
                                          *(_QWORD *)(v491 + 8 * v490 + 8) = 0;
                                          *(_QWORD *)(v491 + 8 * v490 + 16) = 0;
                                        }
                                        else
                                        {
                                          LODWORD(v489) = growOp3((_DWORD)v5, 9, 0, 0, 0);
                                        }
                                        v492 = *((_QWORD *)v5 + 3);
                                        v493 = ~v475;
                                        if ( *(_DWORD *)(v492 + 68) + *(_DWORD *)(v492 + 72) >= 0 )
                                          *(_DWORD *)(*(_QWORD *)(v492 + 80) + 4LL * v493) = *v430;
                                        else
                                          resizeResolveLabel(v492, v5, (unsigned int)v493);
                                        sqlite3VdbeLoadString(v5, 3, "row ");
                                        v494 = *v430;
                                        if ( *v488 > (int)v494 )
                                        {
                                          *v430 = v494 + 1;
                                          v495 = 3 * v494;
                                          v496 = *((_QWORD *)v5 + 17);
                                          *(_DWORD *)(v496 + 8 * v495) = 111;
                                          *(_DWORD *)(v496 + 8 * v495 + 4) = 7;
                                          *(_DWORD *)(v496 + 8 * v495 + 8) = 3;
                                          *(_DWORD *)(v496 + 8 * v495 + 12) = 3;
                                          *(_QWORD *)(v496 + 8 * v495 + 16) = 0;
                                        }
                                        else
                                        {
                                          growOp3((_DWORD)v5, 111, 7, 3, 3);
                                        }
                                        sqlite3VdbeLoadString(v5, 4, " values differ from index ");
                                        v497 = *v430;
                                        v498 = v635 - 1;
                                        if ( *v488 > (int)v497 )
                                        {
                                          *v430 = v497 + 1;
                                          v499 = 3 * v497;
                                          v500 = *((_QWORD *)v5 + 17);
                                          *(_QWORD *)(v500 + 8 * v499) = 9;
                                          *(_DWORD *)(v500 + 8 * v499 + 8) = v498;
                                          *(_DWORD *)(v500 + 8 * v499 + 12) = 0;
                                          *(_QWORD *)(v500 + 8 * v499 + 16) = 0;
                                        }
                                        else
                                        {
                                          growOp3((_DWORD)v5, 9, 0, v498, 0);
                                        }
                                        if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                          v501 = &qword_1803DCAC0;
                                        else
                                          v501 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v489);
                                        *((_DWORD *)v501 + 2) = *v430;
                                      }
                                    }
                                    if ( *(_BYTE *)(v425 + 98) )
                                    {
                                      v502 = v637;
                                      --*((_DWORD *)v637 + 17);
                                      v503 = *((_DWORD *)v502 + 17);
                                      if ( *(_WORD *)(v425 + 94) )
                                      {
                                        v504 = v646;
                                        v505 = 0;
                                        do
                                        {
                                          v506 = *(__int16 *)(v505 + *(_QWORD *)(v425 + 8));
                                          if ( (v506 & 0x8000u) != 0LL || (v639[1][24 * v506 + 8] & 0xF) == 0 )
                                          {
                                            v507 = *v430;
                                            if ( *v645 > (int)v507 )
                                            {
                                              *v430 = v507 + 1;
                                              v508 = 3 * v507;
                                              v509 = *((_QWORD *)v5 + 17);
                                              *(_DWORD *)(v509 + 8 * v508) = 50;
                                              *(_DWORD *)(v509 + 8 * v508 + 4) = v504;
                                              *(_DWORD *)(v509 + 8 * v508 + 8) = v503;
                                              *(_DWORD *)(v509 + 8 * v508 + 12) = 0;
                                              *(_QWORD *)(v509 + 8 * v508 + 16) = 0;
                                            }
                                            else
                                            {
                                              growOp3((_DWORD)v5, 50, v504, v503, 0);
                                            }
                                          }
                                          ++v504;
                                          v505 += 2;
                                        }
                                        while ( v504 - v646 < *(unsigned __int16 *)(v425 + 94) );
                                      }
                                      v426 = v641;
                                      v510 = v641 + v638;
                                      v511 = *v430;
                                      if ( *v645 > (int)v511 )
                                      {
                                        v512 = 3 * v511;
                                        *v430 = v511 + 1;
                                        v513 = *((_QWORD *)v5 + 17);
                                        *(_DWORD *)(v513 + 8 * v512) = 39;
                                        *(_DWORD *)(v513 + 8 * v512 + 4) = v510;
                                        *(_QWORD *)(v513 + 8 * v512 + 8) = 0;
                                        *(_QWORD *)(v513 + 8 * v512 + 16) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v511) = growOp3((_DWORD)v5, 39, v510, 0, 0);
                                      }
                                      v514 = *v430;
                                      if ( *v645 > (int)v514 )
                                      {
                                        *v430 = v514 + 1;
                                        v515 = 3 * v514;
                                        v516 = *((_QWORD *)v5 + 17);
                                        *(_QWORD *)(v516 + 8 * v515) = 9;
                                        *(_DWORD *)(v516 + 8 * v515 + 8) = v503;
                                        *(_DWORD *)(v516 + 8 * v515 + 12) = 0;
                                        *(_QWORD *)(v516 + 8 * v515 + 16) = 0;
                                      }
                                      else
                                      {
                                        growOp3((_DWORD)v5, 9, 0, v503, 0);
                                      }
                                      if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                        v517 = &qword_1803DCAC0;
                                      else
                                        v517 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v511);
                                      v518 = v645;
                                      v519 = v638;
                                      *((_DWORD *)v517 + 2) = *v430;
                                      v520 = v426 + v519;
                                      v521 = *v430;
                                      v522 = *(unsigned __int16 *)(v425 + 94);
                                      if ( *v518 > (int)v521 )
                                      {
                                        *v430 = v521 + 1;
                                        v523 = 3 * v521;
                                        v524 = *((_QWORD *)v5 + 17);
                                        *(_DWORD *)(v524 + 8 * v523 + 4) = v520;
                                        *(_DWORD *)(v524 + 8 * v523 + 12) = v646;
                                        *(_DWORD *)(v524 + 8 * v523) = 64809;
                                        *(_DWORD *)(v524 + 8 * v523 + 8) = v503;
                                        *(_DWORD *)(v524 + 8 * v523 + 16) = v522;
                                      }
                                      else
                                      {
                                        addOp4IntSlow((_DWORD)v5, 41, v520, v503, v646, v522);
                                      }
                                      v525 = *v430;
                                      if ( *v518 > (int)v525 )
                                      {
                                        v526 = 3 * v525;
                                        *v430 = v525 + 1;
                                        v527 = *((_QWORD *)v5 + 17);
                                        *(_QWORD *)(v527 + 8 * v526) = 117;
                                        *(_QWORD *)(v527 + 8 * v526 + 8) = 3;
                                        *(_QWORD *)(v527 + 8 * v526 + 16) = 0;
                                      }
                                      else
                                      {
                                        LODWORD(v525) = growOp3((_DWORD)v5, 117, 0, 3, 0);
                                      }
                                      if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                      {
                                        if ( (int)v525 < 0 )
                                        {
                                          _mm_lfence();
                                          LODWORD(v525) = *v430 - 1;
                                        }
                                        vdbeChangeP4Full(
                                          v5,
                                          *((_QWORD *)v5 + 17) + 24LL * (int)v525,
                                          "non-unique entry in index ",
                                          0);
                                      }
                                      v528 = *v430;
                                      if ( *v518 > (int)v528 )
                                      {
                                        v529 = v635;
                                        *v430 = v528 + 1;
                                        v530 = 3 * v528;
                                        v531 = *((_QWORD *)v5 + 17);
                                        *(_QWORD *)(v531 + 8 * v530) = 9;
                                        *(_QWORD *)(v531 + 8 * v530 + 8) = v529;
                                        *(_QWORD *)(v531 + 8 * v530 + 16) = 0;
                                      }
                                      else
                                      {
                                        growOp3((_DWORD)v5, 9, 0, v635, 0);
                                      }
                                      v532 = *((_QWORD *)v5 + 3);
                                      v533 = ~v503;
                                      if ( *(_DWORD *)(v532 + 68) + *(_DWORD *)(v532 + 72) >= 0 )
                                        *(_DWORD *)(*(_QWORD *)(v532 + 80) + 4LL * v533) = *v430;
                                      else
                                        resizeResolveLabel(v532, v5, (unsigned int)v533);
                                    }
                                    else
                                    {
                                      v426 = v641;
                                    }
                                    if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                      v534 = &qword_1803DCAC0;
                                    else
                                      v534 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (int)v662);
                                    v535 = v659;
                                    *((_DWORD *)v534 + 2) = *v430;
                                    if ( v535 )
                                    {
                                      v536 = (unsigned int)~v535;
                                      v537 = v637[2];
                                      v538 = *(_QWORD *)(v537 + 24);
                                      if ( *(_DWORD *)(v538 + 68) + *(_DWORD *)(v538 + 72) >= 0 )
                                        *(_DWORD *)(*(_QWORD *)(v538 + 80) + 4LL * (int)v536) = *(_DWORD *)(v537 + 144);
                                      else
                                        resizeResolveLabel(v538, v637[2], v536);
                                    }
                                    v427 = v637;
                                  }
                                  v425 = *(_QWORD *)(v425 + 40);
                                  v641 = ++v426;
                                }
                                while ( v425 );
                              }
                            }
                            v268 = v642;
                            v539 = v663;
                            v540 = *v642;
                            if ( *v645 > (int)v540 )
                            {
                              v541 = v647;
                              *v642 = v540 + 1;
                              v542 = 3 * v540;
                              v543 = *((_QWORD *)v5 + 17);
                              *(_DWORD *)(v543 + 8 * v542) = 39;
                              *(_DWORD *)(v543 + 8 * v542 + 4) = v541;
                              *(_DWORD *)(v543 + 8 * v542 + 8) = v539;
                              *(_DWORD *)(v543 + 8 * v542 + 12) = 0;
                              *(_QWORD *)(v543 + 8 * v542 + 16) = 0;
                            }
                            else
                            {
                              growOp3((_DWORD)v5, 39, v647, v663, 0);
                            }
                            if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                              v544 = &qword_1803DCAC0;
                            else
                              v544 = (__int64 *)(*((_QWORD *)v5 + 17) + 24LL * (v539 - 1));
                            v35 = v637;
                            *((_DWORD *)v544 + 2) = *v268;
                            if ( v654 )
                            {
                              v545 = *((unsigned __int16 *)v654 + 47);
                              if ( v545 == 1 )
                              {
                                if ( v644 )
                                {
                                  v546 = *((unsigned __int8 *)v35 + 31);
                                  if ( (unsigned __int8)v546 < 8u )
                                  {
                                    *((_DWORD *)v35 + v546 + 56) = v644;
                                    ++*((_BYTE *)v35 + 31);
                                  }
                                }
                              }
                              else if ( v545 > *((_DWORD *)v35 + 10) )
                              {
                                *((_DWORD *)v35 + 10) = v545;
                                *((_DWORD *)v35 + 11) = v644;
                              }
                            }
                            v298 = v664;
                          }
                          v297 = *(_QWORD *)v648;
                          v648 = v297;
                        }
                        while ( v297 );
                        v287 = Table;
                      }
                      v547 = *(_QWORD **)(v287 + 16);
                      for ( i6 = v664; v547; v547 = (_QWORD *)*v547 )
                      {
                        v548 = v547[2];
                        if ( (!i6 || i6 == v548)
                          && *(_BYTE *)(v548 + 63) == 1
                          && (*(__int16 *)(v548 + 54) > 0
                           || *(_QWORD *)(findElementWithHash(v634 + 67, **(_QWORD **)(v548 + 72), 0) + 16)) )
                        {
                          if ( *(_BYTE *)(v548 + 63) == 1 || *(__int16 *)(v548 + 54) <= 0 )
                            viewGetColumnNames(v637, v548);
                          v549 = *(_QWORD *)(v548 + 80);
                          if ( v549 )
                          {
                            v550 = *(__int64 **)(v549 + 16);
                            if ( v550 )
                            {
                              v551 = *v550;
                              if ( v551 )
                              {
                                if ( *(int *)v551 >= 4 && *(_QWORD *)(v551 + 192) )
                                {
                                  sqlite3VdbeAddOp3((_DWORD)v5, 174, v651, 3, v660);
                                  ++*(_DWORD *)(v548 + 44);
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                  {
                                    freeP4(*(_QWORD *)v5, 4294967280LL, v548);
                                  }
                                  else
                                  {
                                    v552 = 3LL * *v268;
                                    v553 = *((_QWORD *)v5 + 17);
                                    *(_BYTE *)(v553 + 8 * v552 - 23) = -16;
                                    *(_QWORD *)(v553 + 8 * v552 - 8) = v548;
                                  }
                                  v554 = (int)sqlite3VdbeAddOp1(v5, 50, 3);
                                  integrityCheckResultRow(v5);
                                  if ( *(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                                    dword_1803DCAC8 = *v268;
                                  else
                                    *(_DWORD *)(*((_QWORD *)v5 + 17) + 24 * v554 + 8) = *v268;
                                }
                              }
                            }
                          }
                        }
                      }
                      v35 = v637;
                      v269 = v634;
                      v266 = v651;
                    }
                    else
                    {
LABEL_934:
                      v269 = v634;
                    }
                    v267 = DbName;
                  }
                  v651 = ++v266;
                  if ( v266 >= *((_DWORD *)v269 + 10) )
                    goto LABEL_937;
                }
              case 0x16:
                if ( !v37 )
                {
                  v664 = -1;
                  goto LABEL_141;
                }
                v65 = strlen(v37);
                v66 = (__int64 *)off_18026F470;
                v67 = 0;
                while ( 2 )
                {
                  v664 = v67;
                  if ( v66 == &qword_18026F4A0 )
                    goto LABEL_140;
                  v68 = (unsigned __int8 *)*v66;
                  if ( !*v66 )
                    goto LABEL_140;
                  v69 = Str;
                  v70 = v65 & 0x3FFFFFFF;
                  if ( (v65 & 0x3FFFFFFF) == 0 )
                    goto LABEL_134;
                  do
                  {
                    v71 = (unsigned __int8)*v69;
                    --v70;
                    if ( !(_BYTE)v71 || *((_BYTE *)qword_18026E880 + v71) != *((_BYTE *)qword_18026E880 + *v68) )
                      goto LABEL_135;
                    ++v69;
                    ++v68;
                  }
                  while ( v70 > 0 );
LABEL_134:
                  --v70;
LABEL_135:
                  if ( v70 >= 0
                    && *((unsigned __int8 *)qword_18026E880 + (unsigned __int8)*v69) != *((unsigned __int8 *)qword_18026E880
                                                                                        + *v68) )
                  {
                    v67 = (unsigned int)(v67 + 1);
                    ++v66;
                    continue;
                  }
                  break;
                }
                if ( (_DWORD)v67 == 2 )
                {
                  if ( (v634[6] & 0x10000000) == 0 )
                    goto LABEL_144;
LABEL_140:
                  v664 = -1;
                }
                else if ( (_DWORD)v67 != -1 )
                {
                  goto LABEL_144;
                }
LABEL_141:
                if ( !*(_DWORD *)(a3 + 8) )
                {
                  *(_DWORD *)(a3 + 8) = 1;
                  v72 = 0;
                  goto LABEL_145;
                }
LABEL_144:
                v72 = DbName;
LABEL_145:
                v73 = v634;
                v74 = *((_DWORD *)v634 + 10) - 1;
                if ( v74 >= 0 )
                {
                  v75 = v74;
                  v76 = v72;
                  v77 = 32LL * v74;
                  do
                  {
                    if ( *(_QWORD *)(v77 + v73[4] + 8) && (v75 == v76 || !*(_DWORD *)(a3 + 8)) )
                    {
                      *((_DWORD *)v5 + 51) |= 1 << v74;
                      sqlite3VdbeAddOp3((_DWORD)v5, 4, v74, 1, v664);
                    }
                    v73 = v634;
                    --v75;
                    v77 -= 32;
                    --v74;
                  }
                  while ( v74 >= 0 );
                }
                sqlite3VdbeAddOp2(v5, 84, 1, 1);
                goto LABEL_38;
              case 0x17:
                v78 = *(__int64 **)(*(_QWORD *)(v19 + 8) + 8LL);
                v79 = -2;
                v661 = -2;
                v80 = *v78;
                if ( v37 )
                {
                  sqlite3DecOrHexToI64(v37, &v661);
                  v79 = v661;
                  if ( v661 < -1 )
                    v79 = -1;
                }
                if ( v79 >= -1 )
                {
                  v81 = *(_QWORD *)(v80 + 328);
                  *(_QWORD *)(v80 + 208) = v79;
                  if ( v81 )
                    *(_QWORD *)(v81 + 32) = v79;
                }
                returnSingleInt(v5, *(_QWORD *)(v80 + 208));
                goto LABEL_38;
              case 0x19:
                v52 = "exclusive";
                if ( !v37 )
                  goto LABEL_108;
                v53 = v37;
                while ( 2 )
                {
                  v54 = (unsigned __int8)*v53;
                  v55 = (unsigned __int8)v53["exclusive" - v37];
                  if ( (_BYTE)v54 == (_BYTE)v55 )
                  {
                    if ( !(_BYTE)v54 )
                    {
                      v56 = 1;
                      goto LABEL_109;
                    }
                  }
                  else if ( *((unsigned __int8 *)qword_18026E880 + v54) != *((unsigned __int8 *)qword_18026E880 + v55) )
                  {
                    for ( i7 = v37; ; ++i7 )
                    {
                      v58 = (unsigned __int8)*i7;
                      v59 = (unsigned __int8)i7["normal" - v37];
                      if ( (_BYTE)v58 == (_BYTE)v59 )
                      {
                        if ( !(_BYTE)v58 )
                        {
                          v56 = 0;
                          goto LABEL_109;
                        }
                      }
                      else if ( *((unsigned __int8 *)qword_18026E880 + v58) != *((unsigned __int8 *)qword_18026E880 + v59) )
                      {
LABEL_108:
                        v56 = -1;
LABEL_109:
                        if ( !*(_DWORD *)(a3 + 8) )
                        {
                          if ( v56 == -1 )
                          {
                            v29 = v634;
                            v60 = *((unsigned __int8 *)v634 + 105);
LABEL_122:
                            if ( v60 != 1 )
                              v52 = "normal";
                            returnSingleText(v5, v52);
                            goto LABEL_39;
                          }
                          if ( *((int *)v634 + 10) > 2 )
                          {
                            v61 = 64;
                            v62 = 2;
                            do
                            {
                              v63 = **(_QWORD **)(*(_QWORD *)(v61 + v634[4] + 8) + 8LL);
                              if ( !*(_BYTE *)(v63 + 16) )
                              {
                                v64 = *(_QWORD *)(v63 + 328);
                                if ( !v64 || *(_BYTE *)(v64 + 63) != 2 )
                                  *(_BYTE *)(v63 + 8) = v56;
                              }
                              ++v62;
                              v61 += 32;
                            }
                            while ( v62 < *((_DWORD *)v634 + 10) );
                            v5 = v652;
                          }
                          *((_BYTE *)v634 + 105) = v56;
                        }
                        v60 = sqlite3PagerLockingMode(**(_QWORD **)(*(_QWORD *)(v19 + 8) + 8LL), v56);
                        v29 = v634;
                        goto LABEL_122;
                      }
                    }
                  }
                  ++v53;
                  continue;
                }
              case 0x1A:
                v661 = 0;
                sqlite3CodeVerifySchema(v637, (unsigned int)DbName);
                v49 = v657;
                v50 = *((_DWORD *)v637 + 14) + 1;
                *((_DWORD *)v637 + 14) = v50;
                if ( *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v49) == 112 )
                {
                  sqlite3VdbeAddOp2(v5, 178, (unsigned int)DbName, v50);
                }
                else
                {
                  if ( !Str || (unsigned int)sqlite3DecOrHexToI64(Str, &v661) || (v51 = v661, v661 < 0) )
                  {
                    v51 = 0;
                  }
                  else if ( v661 > 4294967294LL )
                  {
                    v51 = -2;
                  }
                  sqlite3VdbeAddOp3((_DWORD)v5, 179, DbName, v50, v51);
                }
                sqlite3VdbeAddOp2(v5, 84, v50, 1);
                goto LABEL_38;
              case 0x1B:
                if ( v37 )
                {
                  sqlite3DecOrHexToI64(v37, &v664);
                  v109 = v664;
                  if ( v664 < 0 )
                  {
                    v109 = qword_180337AE8;
                    v664 = qword_180337AE8;
                  }
                  v110 = v634;
                  if ( !*(_DWORD *)(a3 + 8) )
                    v634[8] = v109;
                  v111 = *((_DWORD *)v634 + 10) - 1;
                  v112 = v111;
                  if ( v111 >= 0 )
                  {
                    v113 = 32LL * v111;
                    do
                    {
                      v114 = *(_QWORD *)(v113 + v110[4] + 8);
                      if ( v114 && (v112 == v39 || !*(_DWORD *)(a3 + 8)) )
                      {
                        *(_QWORD *)(**(_QWORD **)(v114 + 8) + 160LL) = v109;
                        pagerFixMaplimit();
                        v109 = v664;
                        v110 = v634;
                      }
                      v113 -= 32;
                      --v112;
                    }
                    while ( v112 >= 0 );
                  }
                }
                v29 = v634;
                v664 = -1;
                v115 = sqlite3_file_control(v634, v639, 18, &v664);
                if ( v115 )
                {
                  if ( v115 != 12 )
                  {
                    v116 = v637;
                    ++*((_DWORD *)v637 + 12);
                    *((_DWORD *)v116 + 6) = v115;
                  }
                }
                else
                {
                  returnSingleInt(v5, v664);
                }
                goto LABEL_39;
              case 0x1C:
                v29 = v634;
                *((_DWORD *)v637 + 14) = 1;
                v209 = (_QWORD *)v634[68];
                if ( !v209 )
                  goto LABEL_39;
                do
                {
                  sqlite3VdbeMultiLoad(v5, 1, "s", *(_QWORD *)(v209[2] + 8LL), v631);
                  v209 = (_QWORD *)*v209;
                }
                while ( v209 );
                goto LABEL_38;
              case 0x1D:
                LODWORD(v662) = 0;
                v581 = 0;
                v635 = 0;
                if ( v37 )
                {
                  v663 = 0;
                  sqlite3GetInt32(v37, &v663);
                  v582 = v663;
                  if ( (v663 & 2) == 0 )
                    goto LABEL_38;
                  if ( (v663 & 0x10) == 0 )
                  {
                    v583 = v634;
                    v584 = 0;
                    goto LABEL_1005;
                  }
                }
                else
                {
                  v582 = 65534;
                }
                v583 = v634;
                v584 = 2000;
                if ( (unsigned int)(*((_DWORD *)v634 + 182) - 1) <= 0x7CE )
                  v584 = 0;
LABEL_1005:
                v585 = v637;
                v638 = v584;
                v586 = *((_DWORD *)v637 + 13);
                *((_DWORD *)v637 + 13) = v586 + 1;
                if ( v639 )
                  v587 = DbName;
                else
                  v587 = *((_DWORD *)v583 + 10) - 1;
                if ( v39 > v587 )
                  goto LABEL_1052;
                v588 = DbName;
                v648 = (__int64)(v5 + 144);
                v589 = __ROL4__(1, DbName);
                v590 = 32 * v39;
                v591 = v587 - v39 + 1;
                v663 = v589;
                v658 = v591;
                v661 = 32 * v39;
                while ( 1 )
                {
                  if ( v588 == 1 )
                    goto LABEL_1050;
                  v592 = v585;
                  if ( v585[21] )
                    v592 = (__int64 *)v585[21];
                  v593 = *((_DWORD *)v592 + 33);
                  if ( (v589 & v593) == 0 )
                    *((_DWORD *)v592 + 33) = v593 | (1 << v588);
                  v594 = *(_QWORD **)(*(_QWORD *)(v590 + v583[4] + 24) + 16LL);
                  if ( !v594 )
                    goto LABEL_1050;
                  do
                  {
                    v595 = v594[2];
                    if ( !*(_BYTE *)(v595 + 63) )
                    {
                      v596 = *(_BYTE **)v595;
                      v597 = 7;
                      if ( !*(_QWORD *)v595 )
                        goto LABEL_1025;
                      v598 = "sqlite_";
                      do
                      {
                        --v597;
                        if ( !*v596
                          || *((_BYTE *)qword_18026E880 + (unsigned __int8)*v596) != *((_BYTE *)qword_18026E880
                                                                                     + *(unsigned __int8 *)v598) )
                        {
                          goto LABEL_1023;
                        }
                        ++v596;
                        ++v598;
                      }
                      while ( v597 > 0 );
                      --v597;
LABEL_1023:
                      if ( v597 >= 0
                        && *((unsigned __int8 *)qword_18026E880 + (unsigned __int8)*v596) != *((unsigned __int8 *)qword_18026E880
                                                                                             + *(unsigned __int8 *)v598) )
                      {
LABEL_1025:
                        v599 = *(_QWORD *)(v595 + 16);
                        v600 = 0;
                        v601 = *(_WORD *)(v595 + 58);
                        if ( v599 )
                        {
                          do
                          {
                            ++v600;
                            if ( *(char *)(v599 + 100) >= 0 )
                              v601 = -1;
                            v599 = *(_QWORD *)(v599 + 40);
                          }
                          while ( v599 );
                          v585 = v637;
                        }
                        if ( (*(_DWORD *)(v595 + 48) & 0x100) == 0
                          && (v582 & 0x10000) == 0
                          && (!*(_QWORD *)(v595 + 16) || v601 >= 0) )
                        {
                          goto LABEL_1047;
                        }
                        LODWORD(v662) = v662 + 1;
                        if ( (_DWORD)v662 == 2 )
                        {
                          sqlite3BeginWriteOperation(v585, 0, (unsigned int)DbName);
                          LODWORD(v585) = (_DWORD)v637;
                        }
                        v635 += v600 + 1;
                        sqlite3OpenTable((_DWORD)v585, v586, DbName, v595, 112);
                        if ( v601 < 0 )
                        {
                          v603 = v582 & 1;
                          sqlite3VdbeAddOp2(v5, 36, v586, (unsigned int)(v603 + *(_DWORD *)v648 + 2));
                        }
                        else
                        {
                          _mm_lfence();
                          if ( v601 < 33 )
                            v602 = -1;
                          else
                            v602 = v601 - 33;
                          v603 = v582 & 1;
                          sqlite3VdbeAddOp4Int((_DWORD)v5, 33, v586, v603 + *(_DWORD *)v648 + 2, v602, v601 + 33);
                        }
                        v604 = sqlite3MPrintf(
                                 v634,
                                 "ANALYZE \"%w\".\"%w\"",
                                 *(_QWORD *)(v661 + v634[4]),
                                 *(_QWORD *)v595);
                        if ( v603 )
                        {
                          v605 = v637;
                          v606 = *((_BYTE *)v637 + 31);
                          if ( v606 )
                          {
                            v608 = v606 - 1;
                            *((_BYTE *)v637 + 31) = v608;
                            v607 = *((_DWORD *)v605 + v608 + 56);
                          }
                          else
                          {
                            ++*((_DWORD *)v637 + 14);
                            v607 = *((_DWORD *)v605 + 14);
                          }
                          sqlite3VdbeAddOp4((_DWORD)v5, 117, 0, v607, 0, v604, -6);
                          sqlite3VdbeAddOp2(v5, 84, v607, 1);
                          v585 = v605;
LABEL_1047:
                          v584 = v638;
                          goto LABEL_1048;
                        }
                        v584 = v638;
                        sqlite3VdbeAddOp4((_DWORD)v5, 148, v638 != 0 ? 2 : 0, v638, 0, v604, -6);
                        v585 = v637;
                      }
                    }
LABEL_1048:
                    v594 = (_QWORD *)*v594;
                  }
                  while ( v594 );
                  v590 = v661;
                  v589 = v663;
                  v591 = v658;
                  v588 = DbName;
LABEL_1050:
                  v583 = v634;
                  ++v588;
                  v589 = __ROL4__(v589, 1);
                  v590 += 32;
                  --v591;
                  DbName = v588;
                  v658 = v591;
                  v663 = v589;
                  v661 = v590;
                  if ( !v591 )
                  {
                    v581 = v635;
LABEL_1052:
                    sqlite3VdbeAddOp0(v5, 166);
                    v29 = v634;
                    if ( !*((_BYTE *)v634 + 103) && v584 && v581 > 100 )
                    {
                      v610 = (unsigned int)(100 * v584 / v581);
                      if ( 100 * v584 / v581 < 100 )
                        v610 = 100;
                      Op = sqlite3VdbeGetOp(v5, 0, v609, v610);
                      v613 = *((int *)v5 + 36);
                      if ( v613 > 0 )
                      {
                        do
                        {
                          if ( *(_BYTE *)Op == 0x94 )
                            *(_DWORD *)(Op + 8) = v612;
                          Op += 24;
                          --v613;
                        }
                        while ( v613 );
                      }
                    }
                    goto LABEL_39;
                  }
                }
              case 0x1E:
                v40 = *(_QWORD *)(v19 + 8);
                if ( !v37 )
                {
                  if ( v40 )
                    returnSingleInt(v5, *(int *)(*(_QWORD *)(v40 + 8) + 52LL));
                  else
                    returnSingleInt(v5, 0);
                  goto LABEL_38;
                }
                v635 = 0;
                sqlite3GetInt32(Str, &v635);
                v41 = v635;
                v29 = v634;
                *((_DWORD *)v634 + 29) = v635;
                if ( (unsigned int)sqlite3BtreeSetPageSize(v40, v41, 0, 0) == 7 )
                  sqlite3OomFault(v634);
                goto LABEL_39;
              case 0x1F:
                v210 = &off_18026D4E0;
                do
                {
                  sqlite3VdbeMultiLoad(v5, 1, "s", *v210, v631);
                  v210 += 3;
                }
                while ( (__int64)v210 < (__int64)"onoffalseyestruextrafull" );
                goto LABEL_38;
              case 0x20:
                v42 = -1;
                v43 = *(_QWORD *)(v19 + 8);
                if ( !Str )
                  goto LABEL_71;
                if ( (unsigned int)sqlite3StrICmp(Str, "fast") )
                {
                  v48 = getSafetyLevel(Str, 1, 0);
                  v44 = 0;
                  v42 = v48 != 0;
                }
                else
                {
                  v42 = 2;
LABEL_71:
                  v44 = 0;
                }
                if ( !*(_DWORD *)(a3 + 8) && v42 >= 0 )
                {
                  v45 = 0;
                  if ( *((int *)v634 + 10) > 0 )
                  {
                    v46 = 0;
                    do
                    {
                      v47 = *(_QWORD *)(v46 + v634[4] + 8);
                      if ( v47 )
                      {
                        *(_WORD *)(*(_QWORD *)(v47 + 8) + 40LL) &= 0xFFF3u;
                        *(_WORD *)(*(_QWORD *)(v47 + 8) + 40LL) |= 4 * (_WORD)v42;
                      }
                      ++v45;
                      v46 += 32;
                    }
                    while ( v45 < *((_DWORD *)v634 + 10) );
                  }
                }
                if ( v43 )
                {
                  if ( v42 >= 0 )
                  {
                    *(_WORD *)(*(_QWORD *)(v43 + 8) + 40LL) &= 0xFFF3u;
                    *(_WORD *)(*(_QWORD *)(v43 + 8) + 40LL) |= 4 * (_WORD)v42;
                  }
                  v44 = (*(unsigned __int16 *)(*(_QWORD *)(v43 + 8) + 40LL) >> 2) & 3;
                }
                returnSingleInt(v5, v44);
                goto LABEL_38;
              case 0x21:
                v576 = v634;
                if ( *((_BYTE *)v634 + 113) != 118 )
                {
                  if ( (unsigned int)sqlite3SafetyCheckSickOrOk(v634) )
                    sqlite3_log(21, "API call with %s database connection pointer", "unopened");
                  sqlite3_log(
                    21,
                    "%s at line %d of [%.10s]",
                    "misuse",
                    181110,
                    "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
                  goto LABEL_38;
                }
                v577 = v634[3];
                if ( v577 )
                {
                  xmmword_180337A40(v577);
                  v576 = v634;
                }
                if ( *((int *)v576 + 10) > 0 )
                {
                  v578 = 0;
                  v579 = 0;
                  do
                  {
                    v580 = *(_QWORD *)(v579 + v576[4] + 8);
                    if ( v580 )
                    {
                      qword_180337AC8(*(_QWORD *)(*(_QWORD *)(**(_QWORD **)(v580 + 8) + 320LL) + 72LL));
                      v576 = v634;
                    }
                    ++v578;
                    v579 += 32;
                  }
                  while ( v578 < *((_DWORD *)v576 + 10) );
                }
                v28 = v576[3];
                goto LABEL_36;
              case 0x22:
                if ( v37 && !(unsigned int)sqlite3DecOrHexToI64(v37, &v648) )
                  sqlite3_soft_heap_limit64(v648);
                v614 = sqlite3_soft_heap_limit64(-1);
                returnSingleInt(v5, v614);
                goto LABEL_38;
              case 0x23:
                if ( !v37 )
                {
                  returnSingleInt(v5, *(unsigned __int8 *)(v19 + 16) - 1LL);
                  goto LABEL_38;
                }
                v29 = v634;
                if ( *((_BYTE *)v634 + 101) )
                {
                  if ( DbName != 1 )
                  {
                    LOBYTE(v33) = 1;
                    v129 = ((unsigned __int8)getSafetyLevel(v37, 0, v33) + 1) & 7;
                    *(_BYTE *)(v19 + 17) = 1;
                    if ( !v129 )
                      LOBYTE(v129) = 1;
                    *(_BYTE *)(v19 + 16) = v129;
                    setAllPagerFlags(v634);
                  }
                }
                else
                {
                  sqlite3ErrorMsg(v637, "Safety level may not be changed inside a transaction");
                }
                goto LABEL_39;
              case 0x24:
                if ( !v37 )
                  goto LABEL_38;
                sqlite3CodeVerifyNamedSchema(v637, v639);
                v131 = sqlite3LocateTable(v637, 2, Str, v639);
                v648 = v131;
                v132 = v131;
                if ( !v131 )
                  goto LABEL_38;
                v638 = 0;
                v133 = sqlite3PrimaryKeyIndex(v131);
                *((_DWORD *)v637 + 14) = 7;
                v136 = v133;
                v137 = *(_BYTE *)(v132 + 63) == 1;
                v138 = (__int16 *)(v132 + 54);
                Table = v132 + 54;
                v654 = (_QWORD *)v133;
                if ( v137 || *v138 <= (__int16)v134 )
                {
                  viewGetColumnNames(v637, v132);
                  v134 = v638;
                  v135 = 0;
                  v136 = (__int64)v654;
                  Table = v132 + 54;
                }
                LOWORD(v139) = *v138;
                v140 = v135;
                v141 = *(_QWORD *)(v132 + 8);
                if ( (__int16)v135 >= *v138 )
                  goto LABEL_38;
                while ( 1 )
                {
                  v142 = *(_WORD *)(v141 + 18);
                  v143 = v135;
                  if ( (v142 & 0x62) == 0 )
                    goto LABEL_303;
                  if ( *(_QWORD *)(v34 + 16) )
                    break;
                  v638 = ++v134;
LABEL_328:
                  v139 = *v138;
                  ++v140;
                  v136 = (__int64)v654;
                  v141 += 24;
                  if ( v140 >= v139 )
                    goto LABEL_38;
                }
                if ( (v142 & 0x20) != 0 )
                  v143 = 2;
                else
                  v143 = (v142 & 0x40 | 0x20u) >> 5;
LABEL_303:
                if ( (v142 & 1) != 0 )
                {
                  if ( v136 )
                  {
                    v144 = 1;
                    v145 = 1;
                    if ( (__int16)v139 >= 1 )
                    {
                      v146 = (__int16)v139;
                      v147 = *(__int16 **)(v136 + 8);
                      do
                      {
                        if ( *v147 == v140 )
                          break;
                        ++v144;
                        ++v145;
                        ++v147;
                      }
                      while ( v145 <= v146 );
                      v135 = 0;
                    }
                  }
                }
                v148 = *(unsigned __int16 *)(v141 + 16);
                if ( (_WORD)v148 )
                {
                  if ( *(_BYTE *)(v132 + 63) )
                  {
                    v149 = v135;
                  }
                  else
                  {
                    v150 = *(_DWORD **)(v132 + 80);
                    if ( v150 )
                    {
                      if ( *v150 >= (int)v148 )
                        v149 = *(_QWORD *)&v150[8 * v148 - 6];
                      else
                        v149 = v135;
                    }
                    else
                    {
                      v149 = v135;
                    }
                  }
                }
                else
                {
                  v149 = v135;
                }
                if ( v143 < 2 && v149 )
                  v661 = *(_QWORD *)(v149 + 8);
                else
                  v661 = v135;
                v137 = (*(_BYTE *)(v141 + 18) & 4) == 0;
                v663 = *(_DWORD *)(v141 + 8) & 0xF;
                if ( !v137 )
                {
                  v132 = v648;
                  strlen(*(const char **)v141);
                }
                v151 = "issisi";
                if ( *(_QWORD *)(v34 + 16) )
                  v151 = "issisii";
                sqlite3VdbeMultiLoad(v5, 1, v151, (unsigned int)(v140 - v638), *(_QWORD *)v141);
                v134 = v638;
                v135 = 0;
                v138 = (__int16 *)Table;
                goto LABEL_328;
              case 0x25:
                v152 = v639;
                v153 = v639;
                *((_DWORD *)v637 + 14) = 6;
                sqlite3CodeVerifyNamedSchema(v35, v153);
                v154 = v634;
                v635 = 0;
                if ( *((int *)v634 + 10) <= 0 )
                  goto LABEL_387;
                v155 = 0;
                break;
              case 0x26:
                if ( !v37 )
                {
                  v29 = v634;
                  returnSingleInt(v5, *((unsigned __int8 *)v634 + 102));
                  goto LABEL_39;
                }
                v117 = *v37;
                if ( (unsigned __int8)(*v37 - 48) <= 2u )
                {
                  v118 = v117 - 48;
                  goto LABEL_238;
                }
                v119 = v37;
                v120 = "file";
                while ( 2 )
                {
                  v121 = *(unsigned __int8 *)v120;
                  if ( (_BYTE)v117 == (_BYTE)v121 )
                  {
                    if ( !(_BYTE)v117 )
                    {
                      v118 = 1;
LABEL_238:
                      v125 = *v637;
                      if ( *(unsigned __int8 *)(*v637 + 102) != v118 )
                      {
                        v29 = v634;
                        if ( !(unsigned int)invalidateTempStorage(v637) )
                          *(_BYTE *)(v125 + 102) = v118;
                        goto LABEL_39;
                      }
LABEL_38:
                      v29 = v634;
                      goto LABEL_39;
                    }
                  }
                  else if ( *((unsigned __int8 *)qword_18026E880 + (unsigned __int8)v117) != *((unsigned __int8 *)qword_18026E880
                                                                                             + v121) )
                  {
                    for ( i8 = v37; ; ++i8 )
                    {
                      v123 = (unsigned __int8)*i8;
                      v124 = (unsigned __int8)i8["memory" - v37];
                      if ( (_BYTE)v123 == (_BYTE)v124 )
                      {
                        if ( !(_BYTE)v123 )
                        {
                          v118 = 2;
                          goto LABEL_238;
                        }
                      }
                      else if ( *((unsigned __int8 *)qword_18026E880 + v123) != *((unsigned __int8 *)qword_18026E880
                                                                                + v124) )
                      {
                        v118 = 0;
                        goto LABEL_238;
                      }
                    }
                  }
                  LOBYTE(v117) = *++v119;
                  ++v120;
                  continue;
                }
              case 0x27:
                if ( (_BYTE)word_1803379C4 )
                {
                  v126 = xmmword_180337A30(11);
                  if ( v126 )
                    xmmword_180337A40(v126);
                }
                if ( Str )
                {
                  v29 = v634;
                  if ( *Str
                    && ((*(unsigned int (__fastcall **)(_QWORD, char *, __int64, int *))(*v634 + 56LL))(
                          *v634,
                          Str,
                          1,
                          &v663)
                     || !v663) )
                  {
LABEL_249:
                    sqlite3ErrorMsg(v637, "not a writable directory");
                  }
                  else
                  {
                    if ( *((_BYTE *)v634 + 102) <= 1u )
                      invalidateTempStorage(v637);
                    sqlite3_free(sqlite3_temp_directory);
                    if ( *Str )
                      sqlite3_temp_directory = (char *)sqlite3_mprintf("%s", Str);
                    else
                      sqlite3_temp_directory = 0;
                  }
                }
                else
                {
                  returnSingleText(v5, sqlite3_temp_directory);
                  v29 = v634;
                }
LABEL_250:
                if ( (_BYTE)word_1803379C4 )
                {
                  v127 = xmmword_180337A30(11);
                  if ( v127 )
                    xmmword_180337A50(v127);
                }
                goto LABEL_39;
              case 0x28:
                if ( v37 && !(unsigned int)sqlite3DecOrHexToI64(v37, &v648) && v648 >= 0 )
                  sqlite3_limit(v634, 11, v648 & 0x7FFFFFFF);
                v617 = sqlite3_limit(v634, 11, 0xFFFFFFFFLL);
                returnSingleInt(v5, v617);
                goto LABEL_38;
              case 0x29:
                v575 = 0;
                if ( v37 )
                {
                  v663 = 0;
                  sqlite3GetInt32(v37, &v663);
                  sqlite3_wal_autocheckpoint(v634, (unsigned int)v663);
                }
                if ( (__int64 (__fastcall *)())v634[43] == sqlite3WalDefaultHook )
                  v575 = *((_DWORD *)v634 + 88);
                returnSingleInt(v5, v575);
                goto LABEL_38;
              case 0x2A:
                _mm_lfence();
                v571 = 12;
                if ( *(_QWORD *)a3 )
                  v571 = DbName;
                if ( v37 )
                {
                  if ( (unsigned int)sqlite3StrICmp(v37, "full") )
                  {
                    if ( (unsigned int)sqlite3StrICmp(v572, "restart") )
                    {
                      v137 = (unsigned int)sqlite3StrICmp(v574, "truncate") == 0;
                      v573 = 0;
                      if ( v137 )
                        v573 = 3;
                    }
                    else
                    {
                      v573 = 2;
                    }
                  }
                  else
                  {
                    v573 = 1;
                  }
                }
                else
                {
                  v573 = 0;
                }
                *((_DWORD *)v637 + 14) = 3;
                sqlite3VdbeAddOp3((_DWORD)v5, 3, v571, v573, 1);
                sqlite3VdbeAddOp2(v5, 84, 1, 3);
                goto LABEL_38;
              case 0x2B:
                if ( !v37 )
                  goto LABEL_38;
                v627 = 4;
                v628 = "see-";
                v629 = v37;
                do
                {
                  --v627;
                  if ( !*v629
                    || *((_BYTE *)qword_18026E880 + (unsigned __int8)*v629) != *((_BYTE *)qword_18026E880
                                                                               + *(unsigned __int8 *)v628) )
                  {
                    goto LABEL_1110;
                  }
                  ++v629;
                  ++v628;
                }
                while ( v627 > 0 );
                --v627;
LABEL_1110:
                if ( v627 < 0
                  || *((unsigned __int8 *)qword_18026E880 + (unsigned __int8)*v629) == *((unsigned __int8 *)qword_18026E880
                                                                                       + *(unsigned __int8 *)v628) )
                {
                  dword_1803380D4 = strcmp(v37 + 4, "7bb07b8d471d642e") == 0;
                }
                goto LABEL_38;
              case 0x2C:
                if ( v37 )
                {
                  v618 = *(_QWORD *)(v34 + 16);
                  v619 = v37;
                  if ( v618 == 2 || v618 == 3 )
                  {
                    v621 = 0;
                    v622 = 0;
                    v623 = v37;
                    do
                    {
                      v624 = (unsigned __int8)*v623;
                      if ( (*((_BYTE *)&qword_18026E9A0 + v624) & 8) == 0 )
                        break;
                      v622 = ((v624 - 7 * (((char)v624 >> 6) & 1)) & 0xF) + 16 * v622;
                      if ( (v621 & 1) != 0 )
                        *((_BYTE *)v666 + ((unsigned __int64)(unsigned int)v621 >> 1)) = v622;
                      ++v621;
                      ++v623;
                    }
                    while ( v621 < 80 );
                    v5 = v652;
                    v619 = (char *)v666;
                    LODWORD(v620) = (unsigned int)v621 >> 1;
                  }
                  else if ( v618 >= 4 )
                  {
                    LODWORD(v620) = -1;
                  }
                  else
                  {
                    v620 = strlen(v37) & 0x3FFFFFFF;
                  }
                  if ( (*(_BYTE *)(v34 + 16) & 1) != 0 )
                    v625 = sqlite3_rekey_v2(v634, v639, v619, (unsigned int)v620);
                  else
                    v625 = sqlite3_key_v2(v634, v639, v619, (unsigned int)v620);
                  if ( !v625 && (_DWORD)v620 )
                  {
                    sqlite3VdbeSetNumCols(v5, 1);
                    if ( !*(_BYTE *)(*(_QWORD *)v5 + 103LL) )
                    {
                      LOBYTE(v626) = 1;
                      sqlite3VdbeMemSetStr(*((_QWORD *)v5 + 19), "ok", -1, v626, 0);
                    }
                    returnSingleText(v5, "ok");
                  }
                }
                goto LABEL_38;
              default:
                if ( !v37 )
                  goto LABEL_1121;
                v663 = 0;
                sqlite3GetInt32(v37, &v663);
                if ( *((_BYTE *)v634 + 113) == 118 )
                {
                  v630 = v663;
                  if ( v663 > 0 )
                  {
                    sqlite3_busy_handler(v634, sqliteDefaultBusyCallback, v634);
                    v29 = v634;
                    *((_DWORD *)v634 + 183) = v630;
                    returnSingleInt(v5, v630);
                    goto LABEL_39;
                  }
                  sqlite3_busy_handler(v634, 0, 0);
                }
                else
                {
                  if ( (unsigned int)sqlite3SafetyCheckSickOrOk(v634) )
                    sqlite3_log(21, "API call with %s database connection pointer", "unopened");
                  sqlite3_log(
                    21,
                    "%s at line %d of [%.10s]",
                    "misuse",
                    182040,
                    "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
                }
LABEL_1121:
                v29 = v634;
                returnSingleInt(v5, *((int *)v634 + 183));
                goto LABEL_39;
            }
LABEL_332:
            if ( v152 )
            {
              v156 = *(_QWORD *)(v154[4] + v155);
              if ( !v156 || (unsigned int)sqlite3StrICmp(v152, v156) )
              {
                v157 = v634;
                goto LABEL_386;
              }
            }
            v157 = v634;
            v158 = v634[4];
            v159 = *(_QWORD *)(v158 + v155 + 24) + 8LL;
            v160 = *(_DWORD *)(*(_QWORD *)(v158 + v155 + 24) + 12LL);
            if ( v160 )
            {
              do
              {
                v161 = *(_QWORD **)(v159 + 8);
                --v160;
                if ( !v161 )
                  break;
                while ( 1 )
                {
                  v162 = v161[2];
                  if ( !*(_WORD *)(v162 + 54) )
                    break;
                  v161 = (_QWORD *)*v161;
                  if ( !v161 )
                    goto LABEL_357;
                }
                v163 = sqlite3MPrintf(v157, "SELECT*FROM\"%w\"", *(_QWORD *)v162);
                if ( v163 )
                {
                  v661 = 0;
                  sqlite3LockAndPrepare((_DWORD)v157, v163, -1, 0, 0, (__int64)&v661, 0);
                  v164 = v661;
                  if ( v661 )
                  {
                    v165 = *(_QWORD *)v661;
                    if ( *(_QWORD *)v661 )
                    {
                      v166 = *(_QWORD *)(v165 + 24);
                      if ( v166 )
                        xmmword_180337A40(v166);
                      if ( *(__int64 *)(v164 + 184) > 0 )
                        invokeProfileCallback(v165, v164);
                      v167 = sqlite3VdbeReset(v164);
                      sqlite3VdbeDelete(v164);
                      if ( *(_BYTE *)(v165 + 103) || v167 )
                        apiHandleError(v165, v167);
                      sqlite3LeaveMutexAndCloseZombie(v165);
                    }
                    else
                    {
                      sqlite3_log(21, "API called with finalized prepared statement");
                      sqlite3_log(
                        21,
                        "%s at line %d of [%.10s]",
                        "misuse",
                        90759,
                        "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
                    }
                    v157 = v634;
                  }
                  sqlite3DbFreeNN(v157);
                }
                if ( *((_BYTE *)v157 + 103) )
                {
                  sqlite3ErrorMsg(v157[42], "out of memory");
                  *(_DWORD *)(v157[42] + 24LL) = 7;
                }
                v159 = *(_QWORD *)(v157[4] + v155 + 24) + 8LL;
              }
              while ( v160 );
LABEL_357:
              v5 = v652;
            }
            v168 = *(_QWORD **)(v159 + 8);
            if ( !v168 )
              goto LABEL_386;
            v169 = Str;
LABEL_360:
            v170 = (const char **)v168[2];
            if ( v169 )
            {
              if ( !*v170 )
              {
                v157 = v634;
                goto LABEL_383;
              }
              if ( (unsigned int)sqlite3StrICmp(v169, *v170) )
              {
                v157 = v634;
                goto LABEL_382;
              }
            }
            v171 = 7;
            v172 = *v170;
            if ( !*v170 )
              goto LABEL_379;
            v173 = *v170;
            v174 = "sqlite_";
            do
            {
              --v171;
              if ( !*v173
                || *((_BYTE *)qword_18026E880 + *(unsigned __int8 *)v173) != *((_BYTE *)qword_18026E880
                                                                             + *(unsigned __int8 *)v174) )
              {
                goto LABEL_369;
              }
              ++v173;
              ++v174;
            }
            while ( v171 > 0 );
            --v171;
LABEL_369:
            if ( v171 >= 0
              && *((unsigned __int8 *)qword_18026E880 + *(unsigned __int8 *)v173) != *((unsigned __int8 *)qword_18026E880
                                                                                     + *(unsigned __int8 *)v174) )
            {
              goto LABEL_379;
            }
            for ( i9 = (unsigned __int8 *)(v172 + 7); ; ++i9 )
            {
              v176 = *i9;
              v177 = i9["master" - (v172 + 7)];
              if ( (_BYTE)v176 == (_BYTE)v177 )
              {
                if ( !(_BYTE)v176 )
                {
                  v172 = "sqlite_schema";
                  goto LABEL_379;
                }
              }
              else if ( *((unsigned __int8 *)qword_18026E880 + v176) != *((unsigned __int8 *)qword_18026E880 + v177) )
              {
                if ( !(unsigned int)sqlite3StrICmp(v172 + 7, "temp_master") )
                  v172 = "sqlite_temp_schema";
LABEL_379:
                v157 = v634;
                sqlite3VdbeMultiLoad(v5, 1, "sssiii", *(_QWORD *)(v634[4] + v155), (_DWORD)v172);
LABEL_382:
                v169 = Str;
LABEL_383:
                v168 = (_QWORD *)*v168;
                if ( !v168 )
                {
LABEL_386:
                  v154 = v634;
                  v155 += 32;
                  v178 = (int)++v635 < *((_DWORD *)v157 + 10);
                  v152 = v639;
                  if ( !v178 )
                  {
LABEL_387:
                    v29 = v154;
                    goto LABEL_39;
                  }
                  goto LABEL_332;
                }
                goto LABEL_360;
              }
            }
          }
        }
        setPragmaResultColumnNames(v5, v34);
      }
      v37 = Str;
      goto LABEL_61;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180122820  push    rbp
0x180122822  push    rbx
0x180122823  push    rsi
0x180122824  push    r12
0x180122826  push    r14
0x180122828  push    r15
0x18012282a  lea     rbp, [rsp-98h]
0x180122832  sub     rsp, 198h
0x180122839  mov     rax, cs:__security_cookie
0x180122840  xor     rax, rsp
0x180122843  mov     [rbp+0C0h+var_48], rax
0x180122847  mov     rbx, [rcx+10h]
0x18012284b  mov     r12, r9
0x18012284e  mov     rax, [rcx]
0x180122851  mov     r14, r8
0x180122854  mov     [rsp+1C0h+var_150], rcx
0x180122859  mov     rsi, rdx
0x18012285c  mov     [rsp+1C0h+var_160], rax
0x180122861  mov     r15, rcx
0x180122864  mov     [rbp+0C0h+var_F0], rbx
0x180122868  test    rbx, rbx
0x18012286b  jz      short loc_180122873
0x18012286d  mov     [rbp+0C0h+var_D0], rbx
0x180122871  jmp     short loc_1801228A0
0x180122873  cmp     qword ptr [rcx+0A8h], 0
0x18012287b  jnz     short loc_180122887
0x18012287d  test    byte ptr [rax+60h], 8
0x180122881  jnz     short loc_180122887
0x180122883  mov     byte ptr [rcx+23h], 1
0x180122887  call    sqlite3VdbeCreate
0x18012288c  mov     [rbp+0C0h+var_F0], rax
0x180122890  mov     rbx, rax
0x180122893  mov     [rbp+0C0h+var_D0], rax
0x180122897  test    rax, rax
0x18012289a  jz      loc_180122B95
0x1801228a0  movsxd  rcx, dword ptr [rbx+90h]
0x1801228a7  mov     [rsp+1C0h+var_30], rdi
0x1801228af  mov     [rsp+1C0h+var_38], r13
0x1801228b7  cmp     [rbx+94h], ecx
0x1801228bd  jg      short loc_1801228E4
0x1801228bf  xor     eax, eax
0x1801228c1  mov     r13d, 1
0x1801228c7  mov     r9d, r13d
0x1801228ca  mov     [rbp+0C0h+var_B0], rax
0x1801228ce  mov     r8d, r13d
0x1801228d1  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x1801228d5  mov     edx, 0A6h
0x1801228da  mov     rcx, rbx
0x1801228dd  call    growOp3
0x1801228e2  jmp     short loc_18012291E
0x1801228e4  lea     eax, [rcx+1]
0x1801228e7  xor     r15d, r15d
0x1801228ea  mov     [rbx+90h], eax
0x1801228f0  lea     rcx, [rcx+rcx*2]
0x1801228f4  mov     rax, [rbx+88h]
0x1801228fb  mov     edx, 1
0x180122900  mov     [rbp+0C0h+var_B0], r15
0x180122904  mov     [rax+rcx*8+10h], r15
0x180122909  mov     r15, [rsp+1C0h+var_150]
0x18012290e  mov     dword ptr [rax+rcx*8], 0A6h
0x180122915  mov     [rax+rcx*8+4], edx
0x180122919  mov     [rax+rcx*8+8], rdx
0x18012291e  mov     rdi, [r15]
0x180122921  mov     dword ptr [r15+38h], 2
0x180122929  cmp     dword ptr [r14+8], 0
0x18012292e  jbe     short loc_1801229A3
0x180122930  cmp     byte ptr [rdi+0C5h], 0
0x180122937  jz      short loc_18012294D
0x180122939  lea     rdx, aCorruptDatabas; "corrupt database"
0x180122940  mov     rcx, r15
0x180122943  call    sqlite3ErrorMsg
0x180122948  jmp     loc_180122B85
0x18012294d  mov     rdx, rsi
0x180122950  mov     rcx, rdi
0x180122953  mov     r13, r14
0x180122956  call    sqlite3NameFromToken
0x18012295b  mov     rdx, rax
0x18012295e  mov     rcx, rdi
0x180122961  mov     r15, rax
0x180122964  call    sqlite3FindDbName
0x180122969  mov     [rsp+1C0h+var_154], eax
0x18012296d  mov     edx, eax
0x18012296f  test    r15, r15
0x180122972  jz      short loc_180122983
0x180122974  mov     rdx, r15
0x180122977  mov     rcx, rdi
0x18012297a  call    sqlite3DbFreeNN
0x18012297f  mov     edx, [rsp+1C0h+var_154]
0x180122983  test    edx, edx
0x180122985  jns     short loc_1801229B3
0x180122987  lfence
0x18012298a  mov     rcx, [rsp+1C0h+var_150]
0x18012298f  lea     rdx, aUnknownDatabas_0; "unknown database %T"
0x180122996  mov     r8, rsi
0x180122999  call    sqlite3ErrorMsg
0x18012299e  jmp     loc_180122B85
0x1801229a3  movzx   edx, byte ptr [rdi+0C4h]
0x1801229aa  mov     r13, rsi
0x1801229ad  mov     [rsp+1C0h+var_154], edx
0x1801229b1  jmp     short loc_1801229B8
0x1801229b3  mov     r15, [rsp+1C0h+var_150]
0x1801229b8  test    edx, edx
0x1801229ba  js      loc_180122B85
0x1801229c0  lfence
0x1801229c3  mov     rsi, [rsp+1C0h+var_160]
0x1801229c8  movsxd  rdi, edx
0x1801229cb  shl     rdi, 5
0x1801229cf  add     rdi, [rsi+20h]
0x1801229d3  cmp     edx, 1
0x1801229d6  jnz     short loc_1801229E8
0x1801229d8  mov     rcx, r15
0x1801229db  call    sqlite3OpenTempDatabase
0x1801229e0  test    eax, eax
0x1801229e2  jnz     loc_180122B85
0x1801229e8  mov     rdx, r13
0x1801229eb  mov     rcx, rsi
0x1801229ee  call    sqlite3NameFromToken
0x1801229f3  mov     [rbp+0C0h+var_C8], rax
0x1801229f7  mov     r13, rax
0x1801229fa  test    rax, rax
0x1801229fd  jz      loc_180122B85
0x180122a03  cmp     [rbp+0C0h+arg_20], 0
0x180122a0a  mov     rcx, rsi
0x180122a0d  jz      short loc_180122A20
0x180122a0f  mov     r8, r12
0x180122a12  lea     rdx, aT; "-%T"
0x180122a19  call    sqlite3MPrintf
0x180122a1e  jmp     short loc_180122A28
0x180122a20  mov     rdx, r12
0x180122a23  call    sqlite3NameFromToken
0x180122a28  xor     r15d, r15d
0x180122a2b  mov     [rbp+0C0h+Str], rax
0x180122a2f  cmp     [r14+8], r15d
0x180122a33  jbe     short loc_180122A3D
0x180122a35  lfence
0x180122a38  mov     rsi, [rdi]
0x180122a3b  jmp     short loc_180122A40
0x180122a3d  mov     rsi, r15
0x180122a40  mov     r8, r13
0x180122a43  mov     [rbp+0C0h+var_140], rsi
0x180122a47  mov     r13, [rsp+1C0h+var_150]
0x180122a4c  mov     r9, rax
0x180122a4f  mov     rcx, r13
0x180122a52  mov     [rsp+1C0h+var_1A0], rsi
0x180122a57  mov     edx, 13h
0x180122a5c  call    sqlite3AuthCheck
0x180122a61  test    eax, eax
0x180122a63  jnz     loc_180122B5B
0x180122a69  mov     rax, [rbp+0C0h+var_C8]
0x180122a6d  lea     r9, [rbp+0C0h+var_90]
0x180122a71  mov     rcx, [rbp+0C0h+Str]
0x180122a75  mov     r8d, 0Eh
0x180122a7b  mov     [rbp+0C0h+var_88], rax
0x180122a7f  mov     rdx, rsi
0x180122a82  mov     rax, [rsp+1C0h+var_160]
0x180122a87  mov     [rbp+0C0h+var_80], rcx
0x180122a8b  mov     rcx, rax
0x180122a8e  mov     [rbp+0C0h+var_90], r15
0x180122a92  mov     [rbp+0C0h+var_78], r15
0x180122a96  mov     [rax+288h], r15d
0x180122a9d  call    sqlite3_file_control
0x180122aa2  mov     esi, eax
0x180122aa4  test    eax, eax
0x180122aa6  jnz     loc_180122BBD
0x180122aac  mov     esi, 1
0x180122ab1  mov     rcx, rbx
0x180122ab4  mov     edx, esi
0x180122ab6  call    sqlite3VdbeSetNumCols
0x180122abb  mov     r9, [rbp+0C0h+var_90]
0x180122abf  xor     r8d, r8d
0x180122ac2  xor     edx, edx
0x180122ac4  mov     [rsp+1C0h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x180122acd  mov     rcx, rbx
0x180122ad0  call    sqlite3VdbeSetColName
0x180122ad5  mov     rdi, [rbp+0C0h+var_90]
0x180122ad9  test    rdi, rdi
0x180122adc  jz      short loc_180122B5B
0x180122ade  mov     r8, rdi
0x180122ae1  mov     edx, esi
0x180122ae3  mov     rcx, rbx
0x180122ae6  call    sqlite3VdbeLoadString
0x180122aeb  mov     r9d, esi
0x180122aee  mov     r8d, esi
0x180122af1  mov     edx, 54h ; 'T'
0x180122af6  mov     rcx, rbx
0x180122af9  call    sqlite3VdbeAddOp2
0x180122afe  mov     rdi, [rbp+0C0h+var_90]
0x180122b02  test    rdi, rdi
0x180122b05  jz      short loc_180122B5B
0x180122b07  cmp     cs:dword_1803379C0, 0
0x180122b0e  jz      loc_180122BB2
0x180122b14  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x180122b1b  test    rcx, rcx
0x180122b1e  jz      short loc_180122B26
0x180122b20  call    qword ptr cs:xmmword_180337A40
0x180122b26  mov     rcx, rdi
0x180122b29  call    qword ptr cs:xmmword_1803379F0+8
0x180122b2f  dec     cs:qword_1803DC858
0x180122b36  mov     rcx, rdi
0x180122b39  movsxd  rdx, eax
0x180122b3c  sub     cs:qword_1803DC810, rdx
0x180122b43  call    qword ptr cs:xmmword_1803379E0+8
0x180122b49  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x180122b50  test    rcx, rcx
0x180122b53  jz      short loc_180122B5B
0x180122b55  call    qword ptr cs:xmmword_180337A50
0x180122b5b  mov     r15, [rsp+1C0h+var_160]
0x180122b60  lfence
0x180122b63  mov     rdx, [rbp+0C0h+var_C8]
0x180122b67  mov     rcx, r15
0x180122b6a  call    sqlite3DbFreeNN
0x180122b6f  mov     rax, [rbp+0C0h+Str]
0x180122b73  test    rax, rax
0x180122b76  jz      short loc_180122B85
0x180122b78  mov     rcx, [rsp+1C0h+var_160]
0x180122b7d  mov     rdx, rax
0x180122b80  call    sqlite3DbFreeNN
0x180122b85  mov     rdi, [rsp+1C0h+var_30]
0x180122b8d  mov     r13, [rsp+1C0h+var_38]
0x180122b95  mov     rcx, [rbp+0C0h+var_48]
0x180122b99  xor     rcx, rsp; StackCookie
0x180122b9c  call    __security_check_cookie
0x180122ba1  add     rsp, 198h
0x180122ba8  pop     r15
0x180122baa  pop     r14
0x180122bac  pop     r12
0x180122bae  pop     rsi
0x180122baf  pop     rbx
0x180122bb0  pop     rbp
0x180122bb1  retn
0x180122bb2  mov     rcx, rdi
0x180122bb5  call    qword ptr cs:xmmword_1803379E0+8
0x180122bbb  jmp     short loc_180122B5B
0x180122bbd  cmp     esi, 0Ch
0x180122bc0  jz      loc_180122C5A
0x180122bc6  mov     r8, [rbp+0C0h+var_90]
0x180122bca  test    r8, r8
0x180122bcd  jz      short loc_180122C4D
0x180122bcf  lea     rdx, aS_9; "%s"
0x180122bd6  mov     rcx, r13
0x180122bd9  call    sqlite3ErrorMsg
0x180122bde  mov     rbx, [rbp+0C0h+var_90]
0x180122be2  test    rbx, rbx
0x180122be5  jz      short loc_180122C4D
0x180122be7  cmp     cs:dword_1803379C0, 0
0x180122bee  jz      short loc_180122C44
0x180122bf0  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x180122bf7  test    rcx, rcx
0x180122bfa  jz      short loc_180122C02
0x180122bfc  call    qword ptr cs:xmmword_180337A40
0x180122c02  mov     rcx, rbx
0x180122c05  call    qword ptr cs:xmmword_1803379F0+8
0x180122c0b  dec     cs:qword_1803DC858
0x180122c12  mov     rcx, rbx
0x180122c15  movsxd  rdx, eax
0x180122c18  sub     cs:qword_1803DC810, rdx
0x180122c1f  call    qword ptr cs:xmmword_1803379E0+8
0x180122c25  mov     rcx, qword ptr cs:xmmword_1803DC8D0
0x180122c2c  test    rcx, rcx
0x180122c2f  jz      short loc_180122C4D
0x180122c31  call    qword ptr cs:xmmword_180337A50
0x180122c37  inc     dword ptr [r13+30h]
0x180122c3b  mov     [r13+18h], esi
0x180122c3f  jmp     loc_180122B5B
0x180122c44  mov     rcx, rbx
0x180122c47  call    qword ptr cs:xmmword_1803379E0+8
0x180122c4d  inc     dword ptr [r13+30h]
0x180122c51  mov     [r13+18h], esi
0x180122c55  jmp     loc_180122B5B
0x180122c5a  mov     rcx, [rbp+0C0h+var_C8]
0x180122c5e  call    pragmaLocate
0x180122c63  mov     r13, rax
0x180122c66  test    rax, rax
0x180122c69  jz      loc_180122B5B
0x180122c6f  test    byte ptr [rax+9], 1
0x180122c73  mov     rsi, [rsp+1C0h+var_150]
0x180122c78  jz      short loc_180122C8A
0x180122c7a  mov     rcx, rsi
0x180122c7d  call    sqlite3ReadSchema
0x180122c82  test    eax, eax
0x180122c84  jnz     loc_180122B5B
0x180122c8a  movzx   eax, byte ptr [r13+9]
0x180122c8f  test    al, 2
0x180122c91  jnz     short loc_180122CAB
0x180122c93  test    al, 4
0x180122c95  jz      short loc_180122CA0
0x180122c97  mov     r11, [rbp+0C0h+Str]
0x180122c9b  test    r11, r11
0x180122c9e  jnz     short loc_180122CAF
0x180122ca0  mov     rdx, r13
0x180122ca3  mov     rcx, rbx
0x180122ca6  call    setPragmaResultColumnNames
0x180122cab  mov     r11, [rbp+0C0h+Str]
0x180122caf  movzx   eax, byte ptr [r13+8]
0x180122cb4  cmp     eax, 2Ch; switch 45 cases
0x180122cb7  ja      def_180122CD7; jumptable 0000000180122CD7 default case
0x180122cbd  movsxd  rcx, [rsp+1C0h+var_154]
0x180122cc2  lea     r10, cs:180000000h
0x180122cc9  mov     eax, ds:(jpt_180122CD7 - 180000000h)[r10+rax*4]
0x180122cd1  mov     r15, rcx
  ... truncated ...
```
